# **CALCULATOR LIBRARY**

### 1. GENERAL INFO
This is a demo calculator library.

Check out "HOW TO USE THE LIBRARY" portion of this file.

### 2. REQUIREMENTS
See [CalculatorLib.csproj](./CalculatorLib.csproj) for target framework and dependencies.

### 3. FORKING

https://github.com/drago1979/CalculatorLib
### 4. Add GitHub Package Source

To use this package via GitHub Packages, add the GitHub NuGet feed to your system:

```bash
dotnet nuget add source \
  --name "github" \
  --username "drago1979" \
  --password "YOUR_GITHUB_PERSONAL_ACCESS_TOKEN" \
  --store-password-in-clear-text \
  "https://nuget.pkg.github.com/drago1979/index.json"
````  

    ⚠️ Replace YOUR_GITHUB_PERSONAL_ACCESS_TOKEN with a GitHub token that has at least the read:packages scope.

### 5. Install the Package
After adding the source, run:
```bash
dotnet add package CalculatorLib --version 1.0.0
```

### 6. HOW TO USE THE LIBRARY
Most of generally-needed methods can be found in:
```charp
namespace calculator.CalculatorLib
{
    public class Calculator
    {
```

Besides that, some other classes also have public methods in case you choose to access them directly. Eg:

```csharp
namespace calculator.CalculatorLib.Services.Parsers;

public class OperandParser:IParser<Operand>
{
    public Operand Parse(string s)
```

#### 6.1 GET ALLOWED VALUES
Eg.
```csharp
   public class Calculator
    {
        // INPUT VALUES LIMITATIONS
        public static decimal GetMaxDecimalValue()
        {
          return  DecimalConstants.GetMaxDecimalValue();
        }
```

#### 6.2 PARSE USER INPUT
```csharp
   public class Calculator
    {
        // PARSE
        public static decimal ParseDecimal(string s)
        {
            return GetDecimalParser().Parse(s);
        }
```
or

```csharp
public class OperandParser:IParser<Operand>
{
    public Operand Parse(string s)
    {
```

#### 6.3 PERFORM CALCULATION
```csharp
    public class Calculator
    {
        
        public static decimal Calculate(decimal num1, decimal num2, Operand operand)
        {
            return operand.Apply(num1, num2);
        }
```
