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
  Split method into several independent methods that can be called easily.
  

  
