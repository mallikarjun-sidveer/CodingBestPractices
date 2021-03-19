# Purpose of coding standards
  - To follow the consistent coding pattern in your project.
  - Helps the developer to easily read and understand code to resolve issue as soon as based on assumptions and previous experience of developer.
  - For large projects, it helps to maintain the project for future developments changes.
  - To have it in readable format with proper spacing in code blocks.
  - To follow variable and method naming convention in accordance for what they do in logic.
  - To follow commenting with each logical code blocks.
  - Helps in uniform problem solving.
  - Helps in quick code integration and new developer in team.
  - Saves money due to less man hours.


# CodingBestPractices
In this tutorial, we will learn about some of the best practices with C# which we should follow to write better code,
Generally, you need to take care of below things when you want to follow coding standards.

# 1)Naming Conventions:
Naming conventions refers to how we should declare variables.
There are two types which you need to use for naming conventions:

i)PascalCase:
The first characters of all words are Upper Case and other characters are lower case. 
 Example: EmployeeDetails

ii)CamelCase:
The first letter is in lowercase and the first letter of every subsequent concatenated word is in caps.
Example: employeeDetails

To declare variable which returns single entity/object use the following convention,
  var employee=new Employee();

To declare variable which return list of entities/objects, one needs to add suffix ‘s’ or ‘List’ to represent it as list of objects,
  var employees=new Employee();

or
  var employeeList=new Employee();

when you are defining private variable you need to use (_),
  private string _name=”Mallikarjun”;
  

Class         ->    PascalCase    ->    Class EmployeeInfo(){}

Variables     ->    camelCase     ->    string employeeName = "Mallikarjun";

Constructor   ->    PascalCase    ->    EmployeeInfo(){}

Enum          ->    PascalCase    ->    enum EmployeeInfo(){}

Arguments     ->    camelCase     ->    void AddEmployee(string employeeName, int employeeNumber){}

Method        ->    PascalCase    ->    void AddEmployee(){}

Constants     ->    PascalCase    ->    const int EmployeeSalary = 1000;

#   Do Use Meaningful, descriptive words to name variables. Do not use abbreviations.
  Example:
      
      # Correct:
                
                String employeeName;
                
                int employeeSalary;
     
     # Avoid:                
                String empname;
                
                Int sal;
#   Do use PascalCasing for class names and method names.
    Public class Employee
    {
      Public void AddEmployee()
      {
        //..
      }
    }
    
#   Do use camel casing for method arguments and local variables.
    Public void AddEmployee(string employeeName,int employeeSalary)
    {
      //Some code
    }
#   Do not use Underscores in identifiers.
    
    Correct:
            
            EmployeeInfo employeeInfo;
    
    Avoid:
            
            EmployeeInfo employee_Info;
            
#   Do prefix interfaces with the letter I.
    Public interface IEmployee
    {
      //..
    }
    
# Do declare all member variables at the top of a class, with static variables at the very top.
    public class Employee
    {
      Public static string employeeType;
      Public string employeeName{get;set;};
      Public int employeeSalary{get;set};
      
      Public Employee()
      {
        //..
      }
    }
    
 # To check for null or empty conditions, use the following:
      Avoid:
        var employeeName=”testing”;
        if(employeeName!=null && employeeName!=””)
        {
          //..
        }
        
    Correct:
        var employeeName=”testing”;
        if(!string.IsNullOrEmpty(employeeName))
        {
          //..
        }
        
# Avoiding extra braces is also a practice to get into.
  
  Avoid:
        
        var count=10;
        
        if(count>0)
        
        {
          
          count++;
        
        }
  
  Correct:
        
        If(count>0) count++;
        
# Avoid Obsolete Comments
Let us start with Obsolete Comments. According to **Robert C. Martin**:

"_**A comment that has gotten old, irrelevant, and incorrect is obsolete.  Comments get old quickly.  It is best not to write a comment that will become obsolete.  If you find an obsolete comment, it is best to update it or get rid of it as quickly as possible.  Obsolete comments tend to migrate away from the code they once described.  They become floating islands of irrelevance and misdirection in the code.**_"

This is topic create some interesting conversations among all level of developers. Try to avoid comments on individual method or short class. Because most comments i have ever seen is trying to describe the purpose/intentions. Some cases comments are meaningless. Developers writes comments to increase the readability & maintainability . Make sure your comments are not making any noise. It will be great if you could name a method more meaningful instead of comments. I am suggesting because method names are more affective than comments. Most of the comments are meaningless noise. 


Let us check comments below:

  //ensure that we are not exporting
  
  //deleted products
  
  if(product.IsDeleted && !product.IsExported )  
  {  
     ExportProducts = false;     
  }

  // This is a for loop that prints the 1 million times  
  for (int i = 0; i < 1000000; i++)  
  {  
      Console.WriteLine(i);      
  }
  
  
  If we name the method like **CancelExportForDeletedProducts()** instead of comments what will happen? So, method names are more affective than comments. Methods execute and they are real. But comment is good for some cases like, when visual studio will take comments for creating an API documentation and those comments are different, you can use "///" for those comments so that other developers can get intelligence of API or Library. 
  
# Avoid Unnecessary Regions in Class
Regions are a feature of VS that allow you to surround blocks of code. It could be a single or multiple methods. The region exists because it is easier to navigate around the large file. The regions are used to hide ugly code or class that have exploded in size . _If a class does too many things it also violates the Single Responsibility Principle. So next time whenever you will think for adding a new region to your file take step back and ask that is it possible to separate your region into a separate class._

# C# Code Improvement Tips
  
  -> Check Null and Empty condition.
  
  -> Use ternary operator instead of if-else.
  
  -> Use null coalescing operator.
  
  -> Use object initialiser.
  
  -> Use StringBuilder object to append strings, specially when string data is larger.
 
  -> Avoid use of type “var” variables, Create variables with known datatype if you know the datatype of right side of assignment.
  
# Methods rules:
  
  Small.
  
  Do one thing.
  
  Use descriptive names.
  
  Prefer fewer arguments.
  
  Have no side effects.
  
  **Split method into several independent methods that can be called easily.**
  
  According to Refactoring: **Improving the Design of Existing Code by Martin Fowler, Kent Beck (Contributor), John Brant (Contributor), William Opdyke, don Roberts** 

_"Extract Method is one of the most common refactoring I do. I look at a method that is too long or look at code that needs a comment to understand its purpose. I then turn that fragment of code into its own method. I prefer short, well-named methods for several reasons. First, it increases the chances that other methods can use a method when the method is finely grained. Second, it allows the higher-level methods to read more like a series of comments. Overriding also is easier when the methods are finely grained. It does take a little getting used to if you are used to seeing larger methods. And small methods really work only when you have good names, so you need to pay attention to naming. People sometimes ask me what length I look for in a method. To me length is not the issue. The key is the semantic distance between the method name and the method body. If extracting improves clarity, do it, even if the name is longer than the code you have extracted."_

  
