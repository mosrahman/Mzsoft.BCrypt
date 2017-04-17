# Mzsoft.BCrypt #

BCrypt encryption utility implemented blowfish cipher trageted for .NET Standard. Supported platforms are .NET Core, .NET Framework, Mono, Xamarin.iOS, Xamarin.Android, Universal Windows Platform, Windows, Windows Phone also Windows Phone Silverlight
## How to use it ##

Add reference to your code like this.
```csharp
using Mzsoft.BCrypt;
```

To hash a password for the first time, call the ``` HashPassword() ``` method with a random salt, like this:
```csharp
string pass = BCrypt.HashPassword("password", BCrypt.GenerateSalt());
```

To check whether a plain text password matches one that has been hashed previously, use the ``` CheckPassword() ``` method:
```csharp
if (BCrypt.CheckPassword("password", pass)) 
{ 
  Console.WriteLine("Match"); 
} 
else 
{ 
  Console.WriteLine("Don’t Match"); 
}
```
The ``` GenerateSalt() ``` method takes an optional integer parameter that determines the computational complexity of the hashing:
```csharp
string SaltStrong30 = BCrypt.GenerateSalt(30); 
string SaltStrong31 = BCrypt.GenerateSalt(31);
```

The amount of work increases exponentially (2**number). The default number is 10, and the valid range is 4 to 31.
