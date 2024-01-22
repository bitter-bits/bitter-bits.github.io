# Pull request description-like document (write/modify whatever you want, including this title)

```
foreach char c in XML string
    IF isTag
        IF isStartTag   // Push the current XML tag onto the stack
            stack.push(t)

        IF isStartTag   // Verify whether the current XML tag matches the previous tag
            previousTag = '/' + stack.pop()
            IF previousTag != currentTag
                return false
    ELSE
        tokenBuffer.append(c)
return stack.isEmpty()  // Ensure that the stack is empty by the end
```

```console
$ dotnet test

 SimpleXmlValidatorLibrary -> SimpleXmlValidatorLibrary.dll
 SimpleXMLValidatorLibrary.Tests -> SimpleXMLValidatorLibrary.Tests.dll

Test run for SimpleXMLValidatorLibrary.Tests.dll (.NETCoreApp,Version=v7.0)

Starting test execution, please wait...
A total of 1 test files matched the specified pattern.

Passed! -
    Failed: 0, Passed: 1, Skipped: 0, Total: 1,
    Duration: < 1 ms
        - SimpleXMLValidatorLibrary.Tests.dll (net7.0)
```
