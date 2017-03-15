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
assertEquals
assertTrue
assertFalse
assertNull
assertNotNull
assertSame
assertNotSame
fail

# TestSuite - used to organize the test

Used to combine multiple test classes to combine and run

Example : for creating TestSuite

@RunWith(Suite.class)

@Suite.SuiteClasses({TestClass1.class,TestClass2.class})

public class TestSuite{

}

public class TestClass1{

  @Test
  
  public void test1(){

  }
  
  @Test
  
  public void test2(){

  }

}


public class TestClass2{

  @Test
  
  public void test1(){

  }
  
  @Test
  
  public void test2(){

  }

}

# Catergories -

Used to pick specific test methods from multiple test classes to combine and run

@RunWith(Catgories.class)

@IncludeCategory(PostivieTestCases.class)

@ExcludeCategory(PostivieTestCases.class)

@ExcludeCategory(NegativeTestCases.class)

@Suite.SuiteClasses({TestClass1.class,TestClass2.class})

public class TestSuite{

}

public interface PositiveTestCases{

}

public class TestClass1{

  @Test
  
  @Category(PositiveTestCases.class)
  
  public void test1(){

  }
  
  @Test
  
  public void test2(){

  }

}


public class TestClass2{

  @Test
  
  public void test1(){

  }
  
  @Test
  
  @Category(PositiveTestCases.class)
  
  public void test2(){

  }

}

# Parameterized Tests

Sometimes we need to run the same test with multiple times with different test data. To overcome writing multiple test method that differ only by input data Junit introduced parameterized test.


@RunWith(Parameterized.class)
public class ParameterTest{

  private int input;
  private int expected;
  
  @parameters
  public static List Object  data(){
    return Array.asList(Object[][]{
      {5,5},
      {5,10},
      {-12,0},
      {50,50},
      {1,51}
    });
  }
  
  public ParameterTest(int input,int expected){
     this.input = input;
     this.expected = expected;
  }
  
  @Test
  public void test(){
    code
  }
}

# Rule

Rules allow very flexible addition or redefinition of the behavior of each test method in a test class. Testers can reuse or extend one of the provided Rules below, or write their own.

When expecting a exception with message we use Rule instead of @Test(expected=Exception.class)

To use rule decalare

@Rule

public ExpectedException thrown = ExpectedException.none();

@Test

public void Test1(){
  
   thrown.expect(InvalidNumber.class);
   
   thrown.expectMessage("Exception Message");
   
   service.setGoal(-5);
   
}


