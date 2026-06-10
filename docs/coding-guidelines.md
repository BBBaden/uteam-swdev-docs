# Coding Guidelines

## General
- Use English in your code
- Use version control, i.e. use `git`
- Add a `.gitignore` file and exclude compiler output and intermediate files from version control (i.e. `bin/` and `obj/`)
- Add a `readme.md` file explaining setup instructions when needed

### Naming
- Use descriptive names for variables, method names and classes [^1]
```
// ❌ Don't
int d; // elapsed time in days

// ✅ Do
int elapsedTimeInDays;

// ❌ Don't
public List<int[][]> GetThem(int a, int b) {}

// ✅ Do
public List<Cell> GetCellsWithValueInRange(int min, int max) {}

public class Cell {
    int X {get; set;}
    int Y {get; set;}
    int Value {get;}
}
```
- One concept per unit (A class should only contain one concept, a method should do one thing and one thing only) [^2]
- Avoid magic numbers / use searchable names [^3]
```
// ❌ Don't
public double CalculateCircleArea(double radius) {
    return 3.141 * radius * radius;
}
// ✅ Do
private double PI = 3.141;

public double CalculateCircleArea(double radius) {
    return PI * radius * radius;
}

// ...or even better ;)
public double CalculateCircleArea(double radius) {
    return Math.PI * radius * radius;
}
```
- Make differences clear [^4]
```
// ✅ Do
Account GetAccount(UUID accountId);
List<Account> GetActiveAccounts();
AccountInfo GetAccountInfo(UUID accountId);
```
- Use a name from the domain language [^5]
- Encapsulate concepts in classes

### Comments
- Use the least amount of comments possible
- Comments are no replacement for bad code [^6]
- Make intentions clear by code rather than comment [^7]
```
// ❌ Don't
// Check if discount is applicable
if(user.Age >= 18) {}
else if(user.Age <= 65 {}
else {}

// ✅ Do
if(user.IsEligibleForDiscount(user.Age)) {}

public bool IsEligibleForDiscount(int age) {
    return age >= 18 && age <= 65;
}
```
- Remove unused code (Use version control!) [^8]
```
// ❌ Don't
public bool IsEligibleForDiscount(int age) {
    return age >= 18 && age <= 65;
}

/// OLD
///public bool IsEligibleForDiscount(int age, bool hasStudentCard) {
///    return hasStudentCard || age <= 18;
///}
```

## C#, .NET and Tests
- Use the latest LTS version of C# or the .NET framework when creating or updating the course content
- Use modern compiler features such as nullable and implicit global usings
- Use the MSTest framework when writing tests
- Follow the Arange-Act-Assert (AAA) structure [^9]
- Adhere to the best practices suggested by the language definition (https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)

## Linting and code quality
- We use Resharper (or Rider) to statically analyze our code (https://www.jetbrains.com/de-de/resharper/)
- Treat warnings as errors
- Consider using `.editorconfig` files in the top-level
- Exclude build artifacts from the repository with a `.gitignore` file
  - Check https://github.com/github/gitignore for your language
  - Exclude IDE specific files (e.g. `.idea`)

[^1]: Clean Code chapter 2.2
[^2]: Clean Code chapter 2.9, 2.10, 2.12
[^3]: Clean Code chapter 2.6
[^4]: Clean Code chapter 2.4
[^5]: Clean Code chapter 2.14, 2.15
[^6]: Clean Code chapter 4.1
[^7]: Clean Code chapter 4.2
[^8]: Clean Code chapter 4.4
[^9]: Also known as Build-Operate-Check, Clean Code chapter 9.3
