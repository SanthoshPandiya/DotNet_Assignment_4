# DotNet_Assignment_4using System;

namespace StringAssignments
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("=== C# STRING INTERVIEW QUESTIONS (NO LINQ / NO SUBSTRING) ===\n");

            // Q.1: How to reverse a string?
            Console.WriteLine("Q.1: Reverse a String");
            string original = "hello";
            string reversed = "";
            for (int i = original.Length - 1; i >= 0; i--)
            {
                reversed += original[i];
            }
            Console.WriteLine($"Original: {original} | Reversed: {reversed}\n");


            // Q.2: How to find if the given string is a palindrome or not?
            Console.WriteLine("Q.2: Palindrome Check");
            string word = "madam";
            string revWord = "";
            for (int i = word.Length - 1; i >= 0; i--)
            {
                revWord += word[i];
            }
            bool isPalindrome = (word == revWord);
            Console.WriteLine($"Word: {word} | Is Palindrome? {isPalindrome}\n");


            // Q.3: How to reverse the order of words in a given string?
            Console.WriteLine("Q.3: Reverse Order of Words");
            string sentence1 = "C Sharp Programming";
            string[] words1 = sentence1.Split(' ');
            string revSentence = "";
            for (int i = words1.Length - 1; i >= 0; i--)
            {
                revSentence += words1[i] + " ";
            }
            Console.WriteLine($"Original: {sentence1} | Reversed Words: {revSentence.Trim()}\n");


            // Q.4: How to reverse each word in a given string?
            Console.WriteLine("Q.4: Reverse Each Word");
            string sentence2 = "Hello World";
            string[] words2 = sentence2.Split(' ');
            string finalResult = "";
            foreach (string w in words2)
            {
                string tempRev = "";
                for (int i = w.Length - 1; i >= 0; i--)
                {
                    tempRev += w[i];
                }
                finalResult += tempRev + " ";
            }
            Console.WriteLine($"Original: {sentence2} | Each Word Reversed: {finalResult.Trim()}\n");


            // Q.5: How to count the occurrence of each character in a string?
            Console.WriteLine("Q.5: Count Occurrence of Each Character");
            string text = "programming";
            bool[] counted = new bool[text.Length];
            for (int i = 0; i < text.Length; i++)
            {
                if (counted[i]) continue;
                int count = 1;
                for (int j = i + 1; j < text.Length; j++)
                {
                    if (text[i] == text[j])
                    {
                        count++;
                        counted[j] = true;
                    }
                }
                Console.WriteLine($"Character '{text.ToCharArray()[i]}' appears {count} time(s)");
            }
            Console.WriteLine();


            // Q.6: How to remove duplicate characters from a string?
            Console.WriteLine("Q.6: Remove Duplicate Characters");
            string inputStr = "programming";
            string uniqueStr = "";
            for (int i = 0; i < inputStr.Length; i++)
            {
                bool found = false;
                for (int j = 0; j < uniqueStr.Length; j++)
                {
                    if (inputStr[i] == uniqueStr[j])
                    {
                        found = true;
                        break;
                    }
                }
                if (!found)
                {
                    uniqueStr += inputStr[i];
                }
            }
            Console.WriteLine($"Original: {inputStr} | Without Duplicates: {uniqueStr}\n");


            // Q.7: How to find all possible substrings of a given string?
            Console.WriteLine("Q.7: Find All Possible Substrings (Without Substring Function)");
            string subInput = "abc";
            for (int i = 0; i < subInput.Length; i++)
            {
                for (int j = i; j < subInput.Length; j++)
                {
                    // Manually building substring character by character
                    string currentSub = "";
                    for (int k = i; k <= j; k++)
                    {
                        currentSub += subInput[k];
                    }
                    Console.WriteLine(currentSub);
                }
            }
        }
    }
}
