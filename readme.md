# FluenTest

## Low-ceremony tests and fluent assertions

As clean coders, we put a high value on cleanliness in code, especially unit test code.  Because, after all, if a test is not readable, it is not maintainable, and if it is not maintainable, it's worse than no tests at all.

The Nemerle programming language is a particularly clean, readable, and extensible syntax, making it easy to write self-documenting tests that are easy to read, understand, and maintain.

### Fluent Assertions (Syntax extensions in Nemerle)

Fluent assertions are easy to read.  Check these out:

```nemerle

assert char.IsUpper('A') should be true
// In C#:
// Assert.IsTrue(char.IsUpper('A'));

assert "sweet!".Substring(0, 0) should be ""
// In C#:
// Assert.AreEqual("", "sweet!".Substring(0, 0));

assert "cool!".Substring(0, 0) should refer to string.Empty
// In C#:
// Assert.IsTrue(ReferenceEquals(string.Empty, "cool!".Substring(0, 0)));

assert 5 should match IsOdd
// In C#:
// Assert.IsTrue(IsOdd(5));

assert _ = "throw".Substring(-1,0) should throw ArgumentException
// In C# (roughly equivalent):
// bool exceptionThrown = false;
// try
// {
//    "throw".Substring(-1,0);
// }
// catch(ArgumentException)
// {
//    exceptionThrown = true;
// }
// if(!exceptionThrown)
//    Assert.Fail("Expected ArgumentException, but no exception was thrown.");
```

