# HackerRank Anotações
Math.pow(2,z) #Para calcular exponenciação 2^z
scanner.hasNext() #Verificar se é o fim da entrada

## Java Loops ||
import java.util.*;
public class Solution {
    
    static int getValue(int a,int b, int n) {
    	
        int sum = a;
        for(int z=n;z>=0;z--) {
            sum = sum + ((int) Math.pow(2,z))*b;
        }       
        return sum;
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int t = 0;
        int a = 0;
        int b = 0;
        int n = 0;
        t = in.nextInt();
        for(int i=0;i<t;i++) {
            a = in.nextInt();
            b = in.nextInt();
            n = in.nextInt();
            for(int j =0;j<n;j++) {
                System.out.print(getValue(a,b,j)+" ");
            }
            System.out.println();
        }
    }
}

## Java Datatypes
import java.util.*;
import java.io.*;
import java.math.BigInteger;

class Solution{
    public static void main(String []argh)
    {
        Scanner sc = new Scanner(System.in);
        int t=sc.nextInt();

        for(int i=0;i<t;i++)
        {
            try
            {
                long x=sc.nextLong();
                
                System.out.println(x+" can be fitted in:");
                if(x>=(Byte.MIN_VALUE) && x<=Byte.MAX_VALUE)System.out.println("* byte");
                if(x>=(Short.MIN_VALUE) && x<=Short.MAX_VALUE)System.out.println("* short");
                if(x>=(Integer.MIN_VALUE) && x<=Integer.MAX_VALUE)System.out.println("* int");
                if(x>=(Long.MIN_VALUE) && x<=Long.MAX_VALUE)System.out.println("* long");   
            }
            catch(Exception e)
            {
                System.out.println(sc.next()+" can't be fitted anywhere.");
            }
        }
    }
}

## Java End-of-file
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        String line;
        int i = 1;
        while(scanner.hasNext()) {
            line = scanner.nextLine();
            System.out.println(i + " " +line);
            i++;
        }
        
    }
}

## Java Static Initializer Block
import java.io.*;
import java.util.*;

public class Solution {

    static int n1;
    static int n2;
    static boolean flag;
    
    static {
        Scanner scanner = new Scanner(System.in);
        n1 = scanner.nextInt();
        n2 = scanner.nextInt();
        
        if(n1 > 0 && n2 > 0) {
             flag = true;
         } else {
             System.out.println("java.lang.Exception: Breadth and height must be positive");
         }
    }
        
    public static void main(String[] args) {
        
        if(flag) {
            int area = n1 * n2;
            System.out.println(area);
        }
         
    }
}

## Java Int to String
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        int n = scanner.nextInt();
        scanner.close();
        String str = String.valueOf(n);
        
        if(str instanceof String) {
            System.out.println("Good job");
        } else {
            System.out.println("Wrong answer");
        }
    }
}

## Java Date and Time
class Result {

    /*
     * Complete the 'findDay' function below.
     *
     * The function is expected to return a STRING.
     * The function accepts following parameters:
     *  1. INTEGER month
     *  2. INTEGER day
     *  3. INTEGER year
     */

    public static String findDay(int month, int day, int year) {
        Calendar cal = Calendar.getInstance();
        
        cal.set(Calendar.MONTH, month -1);
        cal.set(Calendar.DAY_OF_MONTH, day);
        cal.set(Calendar.YEAR, year);
        
        return cal.getDisplayName(Calendar.DAY_OF_WEEK, Calendar.LONG, Locale.US).toUpperCase();
    }

}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        String[] firstMultipleInput = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");

        int month = Integer.parseInt(firstMultipleInput[0]);

        int day = Integer.parseInt(firstMultipleInput[1]);

        int year = Integer.parseInt(firstMultipleInput[2]);

        String res = Result.findDay(month, day, year);

        bufferedWriter.write(res);
        bufferedWriter.newLine();

        bufferedReader.close();
        bufferedWriter.close();
    }
}

## Java Strings Introduction
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        /* Save input */
        Scanner scan = new Scanner(System.in);
        String A = scan.next();
        String B = scan.next();
        scan.close();
        
        /* Sum lengths */
        System.out.println(A.length() + B.length());

        /* Compare lexicographical ordering */
        System.out.println(A.compareTo(B) > 0 ? "Yes" : "No");
        
        /* Print the Strings in desired format */
        System.out.println(capFirstLetter(A) + " " + capFirstLetter(B));
    }
    
    private static String capFirstLetter(String str) {
        if (str == null || str.length() == 0) {
            return "";
        } else {
            return str.substring(0,1).toUpperCase() + str.substring(1);
        }
    }
}

## Substring Java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String str = scan.next();
        int start  = scan.nextInt();
        int end    = scan.nextInt();
        scan.close();
        
        System.out.println(str.substring(start, end));
    }
}

## Java Substring Comparisons
import java.util.Scanner;
public class Solution {

    public static String getSmallestAndLargest(String s, int k) {
        String menor = "";
        String maior = "";
         
        menor = s.substring(0, k);
        maior = s.substring(0, k);
        
        for(int i=0; i <= s.length()- k; i++) {
            String str = s.substring(i, k+i);
            if(menor.compareTo(str) > 0) {
                menor = str;
            }
            if(maior.compareTo(str) < 0) {
                maior = str;
            }
        }
        
        return menor + "\n" + maior;
    }
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String s = scan.next();
        int k = scan.nextInt();
        scan.close();
      
        System.out.println(getSmallestAndLargest(s, k));
    }
}

## Java String Reverse
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner sc=new Scanner(System.in);
        String A=sc.next();
        
        String reverse = new StringBuilder(A).reverse().toString();
        
        System.out.println(A.equals(reverse) ? "Yes" : "No");
    }
}

## Java String Tokens
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String a = scanner.nextLine();
        scanner.close();
         
        a = removeLeadingNonLetters(a);
         
        if(a.length() == 0) {
            System.out.println(0);
            return;
        }
        
        String[] arr = a.split("[^A-Za-z]+");
        
        System.out.println(arr.length);
        
        for(String i : arr) {
            System.out.println(i);
        }
    }
    
     private static String removeLeadingNonLetters(String str) {
        int i;
        for (i = 0; i < str.length(); i++) {
            if (Character.isLetter(str.charAt(i))) {
                break;
            }
        }
        return str.substring(i);
    }
}

## Pattern Syntax Checker
import java.io.*;
import java.util.*;
import java.util.regex.Pattern;

public class Solution {

    public static void main(String[] args) {
       Scanner scanner = new Scanner(System.in);
       
       int quant = Integer.parseInt(scanner.nextLine());
       
       while(quant > 0) {
           String test = scanner.nextLine();
           
           try {
               Pattern pat = Pattern.compile(test);
               System.out.println("Valid");
           } catch(Exception e) {
               System.out.println("Invalid");
           }
           quant--;
       }
    }
}

## Java Regex
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
    Scanner in = new Scanner(System.in);
        while(in.hasNext()) {
            String IP = in.next();
            System.out.println(IP.matches(new MyRegex().pattern));
        }
    }
}

class MyRegex {
    String num = "([01]?\\d{1,2}|2[0-4]\\d|25[0-5])";
    String pattern = num + "." +  num + "." +  num + "." + num;
}
