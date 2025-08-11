# **CALCULATOR LIBRARY**

### 1. GENERAL INFO
This is a demo calculator library.
Latest version: 1.0.8


### 2. REQUIREMENTS
See [CalculatorLib.csproj](./CalculatorLib.csproj) for target framework and dependencies.

### 4. INSTALLATION - via NuGet package

1. Create NuGet.config file in your solution/project:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
    <add key="github" value="https://nuget.pkg.github.com/drago1979/index.json" />
  </packageSources>
  <packageSourceCredentials>
    <github>
      <add key="Username" value="YOUR_GITHUB_USERNAME" />
      <add key="ClearTextPassword" value="YOUR_GITHUB_PERSONAL_ACCESS_TOKEN" />
    </github>
  </packageSourceCredentials>
</configuration>
````  

    ⚠️ Replace: YOUR_GITHUB_USERNAME with your username.
    ⚠️ Replace: YOUR_GITHUB_PERSONAL_ACCESS_TOKEN with a GitHub token that has at least the read:packages scope.
    ⚠️ Warning: Exclude the NuGet.config from versioning to keep your GitHub token safe.

2. Install the Package
After adding the source, run:
```bash
dotnet add package CalculatorLib --version 1.0.1
```
### 4. INSTALLATION - via Source Code
1. Clone the repository:
``` bash
git clone https://github.com/drago1979/CalculatorLib.git
```
2. Copy the CalculatorLib directory into your solution folder or add it as an existing project.

3. Add a project reference from your main project to CalculatorLib:
``` bash
dotnet add <YourProject>.csproj reference CalculatorLib/CalculatorLib.csproj
```

### 6. HOW TO USE THE LIBRARY - NuGet package

#### => Include it in file
```csharp
using CalculatorLib;
```

#### => Most of generally-needed methods can be found in Calculator class.

![Calculator class methods](Documentation/calculator_class_methods.jpg)


Besides that, some other classes also have public methods in case you choose to access them directly. Eg:

![Input type decimal - methods](Documentation/input_type_decimal_methods.jpg)

or

![Input type operand - methods](Documentation/input_type_operand_methods.jpg)

#### 6.1 GET ALLOWED VALUES

```csharp
    public void Test()
    {
        Calculator.GetMaxDecimalValue();
        Calculator.GetMinDecimalValue();
        Calculator.GetOperandValues();

        InputTypeDecimal.GetMaxValue();
        InputTypeDecimal.GetMinValue();
        
    }

```

#### 6.2 PARSE USER INPUT
```csharp
    public void Test()
    {
        var num = InputTypeDecimal.Parse("6");
        
        var operand = InputTypeOperand.Parse("/");
    }
````    

#### 6.3 PERFORM CALCULATION
```csharp
    public void Test()
    {
        var num1 = InputTypeDecimal.Parse("6");
        var num2 = InputTypeDecimal.Parse("3");
        
        var operand = InputTypeOperand.Parse("/");
        
        
        var result = Calculator.Calculate(num1, num2, operand);
    }
```

#### => Additional details can be found in source code.
