# Testing
A cloud native application is optimized for fast feedback at every tier, from components all the way to entire systems. Testing is the primary way to drive that feedback loop.

-

As applications become increasingly distributed, the strategies for how we effectively write tests change considerably.

The practice of `integration testing` focuses on writing and executing tests against a group of software modules that depend on one another.

-

Integration testing is a standard practice in software development where developers who are working on separate modules or components are able to automate a set of test cases which exist to ensure that the expected functionality of integration remains true

-

It can often be the case that integration testing requires executing tests in a shared integration environment. In this scenario, applications may be subject to concurrently sharing external resources, such as a database or an application server.

-
-

# The Makeup of a Test

Whatever your organizational approach, be sure that you automate running all the tests before promoting a binary closer to production.


-
-

# Testing in Spring Boot

Testing in Spring Boot applications breaks down into two separate styles of testing: unit tests and integration tests. An integration test is any test that requires access to the Spring application context (the ApplicationContext) during test execution. 

-
The main difference between the two styles of tests is that integration tests require a Spring context to test the integration between different components, and unit tests will test individual components without any dependency on the Spring libraries.
-

make sure to include spring-boot-starter-test as a dependency

-
e.g
```
@SpringBootTest
@RunWith(SpringRunner.class)
public class ApplicationContextTests {

 @Autowired
 private ApplicationContext applicationContext;

 @Test
 public void contextLoads() throws Throwable {
  Assert.assertNotNull("the application context should have loaded.",
   this.applicationContext);
 }
}
```

-
The @RunWith annotation is specific to the JUnit framework. The @RunWith annotation tells JUnit which test runner strategy to use. In this case, we want to run our test with the Spring TestContext Framework, a module in the Spring Framework that provides generic test support for Spring applications.
-

The @SpringBootTest annotation indicates that this class is a Spring Boot test class, and provides support to scan for a ContextConfiguration that tells the test class how to load the ApplicationContext.

-
-

# Integration Testing

-

## Mocking in Tests
Mocking is usually talked about in the context of unit testing. In the simplest sense, `mock objects` allow us to isolate parts of the system under test by replacing collaborating components of a module with a simulated object that targets testing behavior in a controlled way. 

-

If one service module of an application requires access to an external backing service, perhaps taking the form of a call to another microservice, we can plug in a fake implementation of that backing service so that it becomes an invariant. 

The only variant is the component under test and its interaction with the mock.

-

Spring Boot supports the @MockBean annotation. @MockBean instructs Spring to provide a mock of a bean in the application context, and to effectively mute the definition of the original, live bean in the application context.

It creates a Mockito mock for a bean inside the ApplicationContext

-

```
 @MockBean
 private UserService userService;

 @MockBean
 private AccountRepository accountRepository;
```
Creates a Mockito mock for the UserService component.

-

```
 @Before
 public void before() {
  accountService = new AccountService(accountRepository, userService); 2
 }
```
Creates a new instance of the AccountService with mocked components as parameters.

-

```
 @Test
 public void getUserAccountsReturnsSingleAccount() throws Exception {
  given(this.accountRepository.findAccountsByUsername("user")).willReturn(
   Collections
    .singletonList(new Account("user", new AccountNumber("123456789"))));

```
Stubs the repository method call to findAccountsByUsername(String username) with an Account list.

-
```
 given(this.userService.getAuthenticatedUser()).willReturn(
   new User(0L, "user", "John", "Doe")); 
```
Stubs the method call to getAuthenticatedUser() with a new instance of User.

-
```
 List<Account> actual = accountService.getUserAccounts();5
```
Calls the getUserAccounts() method of the AccountService while using the defined mocks.
@RunWith(SpringRunner.class) annotation—indicating that no ApplicationContext will be loaded during test execution. 

-

In this unit test, we are able to test the functionality of the AccountService without making remote HTTP calls to a backing service inside the UserService bean. The same applies for the AccountRepository component.

-

## Working with the Servlet Container in @SpringBootTest

The @SpringBootTest annotation should be used when you want to write integration tests on a fully configured ApplicationContext in a Spring Boot application.

This annotation will also allow you to configure the servlet environment for your test context. @SpringBootTest supports a webEnvironment attribute to describe how Spring Boot should configure the embedded servlet container that your application uses at runtime.

-

### webEnvironment attribute
`MOCK`: Loads a WebApplicationContext and provides a mock servlet environment.
`DEFINED_PORT`: Loads an EmbeddedWebApplicationContext and provides a real servlet environment on a defined port.

`RANDOM_PORT`: Loads an EmbeddedWebApplicationContext and provides a real servlet environment on a random port.

`NONE`: Loads an ApplicationContext using SpringApplication but does not provide any servlet environment (mock or otherwise).

-

## Slices

Spring Boot provides multiple testing annotations that target a specific slice of your application.

-

```@JSONTEST```
The @JsonTest annotation allows you to activate just the configuration to test JSON serialization and deserialization.

-

```
@Autowired
 private JacksonTester<User> json;
 ...
  assertThat(this.json.write(user)).isEqualTo("user.json");
  assertThat(this.json.write(user)).isEqualToJson("user.json");
  assertThat(this.json.write(user)).hasJsonPathStringValue("@.username");

  assertJsonPropertyEquals("@.username", "user");
  assertJsonPropertyEquals("@.firstName", "Jack");
  assertJsonPropertyEquals("@.lastName", "Frost");
  assertJsonPropertyEquals("@.email", "jfrost@example.com");
```

-
AssertJ-based JSON tester backed by Jackson.

Write the User object to JSON and compare to the user.json file.

Asserts that the actual JSON result matches for an expected property value.

-

```@WEBMVCTEST```
The @WebMvcTest annotation supports testing individual Spring MVC controllers in a Spring Boot application. This annotation auto-configures the necessary Spring MVC infrastructure needed to test interactions with controller methods

-

```
@Autowired
 private MockMvc mvc; 1

 @MockBean
 private AccountService accountService; 2

 @Test
 public void getUserAccountsShouldReturnAccounts() throws Exception {
  String content = "[{\"username\": \"user\", \"accountNumber\": \"123456789\"}]";

  3
  given(this.accountService.getUserAccounts()).willReturn(
   Collections.singletonList(new Account("user", "123456789")));

  4
  this.mvc.perform(get("/v1/accounts").accept(MediaType.APPLICATION_JSON))
   .andExpect(status().isOk()).andExpect(content().json(content));
 }
```

-

1. Mock the MVC client for performing HTTP requests to Spring MVC controllers.

2. Mocks the AccountService component that collaborates with the AccountController.

3. Define the expected behavior of retrieving user accounts from the accountService bean.

4. Finally, use the MockMvc client to assert for an expected HTTP result from the AccountController.

-