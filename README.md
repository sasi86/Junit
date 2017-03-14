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
