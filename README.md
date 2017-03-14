# Junit

Junit Basics

Junit Test Method

method - annotated with @Test
Example:
@Test
public void testMethod(){

}

# Basic Annotation - Method Level

@Test

@Before - called before each methods in the test class are executed

@After - called after each methods in the test class are executed

@BeforeClass - called before any methods in the test class are executed

@AfterClass - called after all the methods in the test class are executed

@Ignore- temproraliy disables the test from being executed

@Test(expected=Exception.class)

@Test(timeout=100)

# Assertion Basics

assertArrayEquals
