# String-Manipulation---Anagram-Check-Java-
import java.util.Arrays;
import java.util.Scanner;

public class AnagramChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input two strings
        System.out.print("Enter the first string: ");
        String str1 = scanner.nextLine();

        System.out.print("Enter the second string: ");
        String str2 = scanner.nextLine();

        // Check if they are anagrams
        boolean result = areAnagrams(str1, str2);

       
        System.out.println("Are the strings anagrams? " + result);

        scanner.close();
    }

   
    public static boolean areAnagrams(String str1, String str2) {
        
        str1 = str1.replaceAll("\\s", "").toLowerCase();
        str2 = str2.replaceAll("\\s", "").toLowerCase();

        
        if (str1.length() != str2.length()) {
            return false;
        }

        
        char[] charArray1 = str1.toCharArray();
        char[] charArray2 = str2.toCharArray();

       
        Arrays.sort(charArray1);
        Arrays.sort(charArray2);

        // Compare the sorted arrays
        return Arrays.equals(charArray1, charArray2);
    }
}
