# Part1
**1. failure-inducing input:
`public class ArrayTests {
  @Test 
   public void testReverseInPlace() {
    int[] input1 = {3,2};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{2,3}, input1);
 }`

**2. input that does not induce error:
`@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }`


**3. symptom
![Image]()


**4. bug
-Previous:
![Image]()

-After fix:
![Image]()

**5
This issue with previous code is because it is assigning value to itself. Thus, elements in `arr` will be mixed up during the process of re-assigning. We need to create a new array called `newArray` in this code to hold the reversed order of `arr` through calling method `reversed`. Then, we can assign the elements in `newArray` to `arr` to change the input array in reversed order. Then the tests should pass. See below
![Image]()

# Part2

