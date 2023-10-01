import java.util.Random;
import java.util.*;
public class Main
{
   public static void main(String[] args)
   {
      Scanner sc=new Scanner(System.in);
      System.out.println(" PASSWORD GENERATOR");
      System.out.println("-------------------");
      System.out.println("-------------------");
      System.out.println("This generator allows you to generate random passwords of desired length");
      System.out.println("-------------------");
      System.out.println("4 level of passwords can be generated");
      System.out.println("Level 1 -> Lowercase Letters");
      System.out.println("Level 2 -> Lowercase & Uppercase letters");
      System.out.println("Level 3 -> Lowercase, Uppercase letters and numbers");
      System.out.println("Level 4 -> Lowercase, Uppercase letters, numbers and special characters");
      System.out.println("-------------------");
      System.out.print("Length of password : ");
      int len=sc.nextInt();
      System.out.print("Level of password (1-4) : ");
      int level=sc.nextInt();
      System.out.println(generatePassword(len, level));
   }

   private static char[] generatePassword(int length,int level) 
   {
      String capitalCaseLetters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
      String lowerCaseLetters = "abcdefghijklmnopqrstuvwxyz";
      String specialCharacters = "!@#$";
      String numbers = "1234567890";
      String combinedChars = capitalCaseLetters + lowerCaseLetters + specialCharacters + numbers;
      String combined="";
      Random random = new Random();
      char[] password = new char[length];

      if(level == 1)
      {
          password[0] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[1] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[2] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[3] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          combined=lowerCaseLetters;
      }
      if(level == 2)
      {
          password[0] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[1] = capitalCaseLetters.charAt(random.nextInt(capitalCaseLetters.length()));
          password[2] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[3] = capitalCaseLetters.charAt(random.nextInt(capitalCaseLetters.length()));
          combined=lowerCaseLetters+capitalCaseLetters;
      }
      if(level==3)
      {
          password[0] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[1] = capitalCaseLetters.charAt(random.nextInt(capitalCaseLetters.length()));
          password[2] = numbers.charAt(random.nextInt(numbers.length()));
          password[3] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
      
      combined=lowerCaseLetters+capitalCaseLetters+numbers;
      }
      if(level ==4)
      {
          password[0] = lowerCaseLetters.charAt(random.nextInt(lowerCaseLetters.length()));
          password[1] = capitalCaseLetters.charAt(random.nextInt(capitalCaseLetters.length()));
          password[2] = specialCharacters.charAt(random.nextInt(specialCharacters.length()));
          password[3] = numbers.charAt(random.nextInt(numbers.length()));
      
          combined=lowerCaseLetters+capitalCaseLetters+numbers+specialCharacters;
      }
      //String str="";
      for(int i = 4; i< length ; i++) 
      {
         password[i] = combined.charAt(random.nextInt(combined.length()));
         //str+=password[i];
      }
      return password;
      //System.out.println("Your "+length+" letter Level "+level+"password is : "+password);
   }
   
}