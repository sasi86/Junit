# Junit

Junit Basics

Junit Test Method

method - annotated with @Test
Example:
@Test
public void testMethod(){

}

Basic Annotation - Method Level
@Test
@Before
@After
@BeforeClass - called before any methods in the test class are executed
@AfterClass - called after all the methods in the test class are executed
@Ignore- temproraliy disables the test from being executed
@Test(expected=Exception.class)
@Test(timeout=100)
