//Easy interview Problem
//Solving the following
import java.util.*;
public class EasyProblems {
    public int[] twoSum(int[] nums, int target) {

        HashMap<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {

            int complement = target - nums[i];

            if (map.containsKey(complement)) {
                return new int[]{map.get(complement), i};
            }

            map.put(nums[i], i);
        }

        return new int[0];
    }
    public int reverse(int x) {

        int reversed = 0;

        while (x != 0) {

            int digit = x % 10;
            if (reversed > Integer.MAX_VALUE / 10 ||
                reversed < Integer.MIN_VALUE / 10) {
                return 0;
            }

            reversed = reversed * 10 + digit;

            x = x / 10;
        }

        return reversed;
    }
    public boolean isPalindrome(int x) {

        if (x < 0) {
            return false;
        }

        int original = x;
        int reversed = 0;

        while (x != 0) {

            int digit = x % 10;

            reversed = reversed * 10 + digit;

            x = x / 10;
        }

        return original == reversed;
    }

    public static void main(String[] args) {

        EasyProblems ep = new EasyProblems();

        System.out.println("Testing easy problems...");
        int[] nums = {2, 7, 11, 15};
        int target = 9;

        int[] result = ep.twoSum(nums, target);

        System.out.println("Two Sum Indices: "
                + result[0] + " " + result[1]);
        int number = 12345;

        System.out.println("Reversed Integer: "
                + ep.reverse(number));
        int palindromeNumber = 121;

        System.out.println("Is Palindrome: "
                + ep.isPalindrome(palindromeNumber));
    }
}
output:
Testing easy problems...
Two Sum Indices: 0 1
Reversed Integer: 54321
Is Palindrome: true
