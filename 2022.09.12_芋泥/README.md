# Pull request description-like document (write/modify whatever you want, including this title)


```console
FOR i = 0 TO xml.size - 1
    IF '<' AND  insideTag : return false
    IF '>' AND !insideTag : return false

    IF '<' AND !insideTag                   // enter a new tag
        insideTag= true
        begin = i + 1
        CONTINUE

    IF '>' AND token[0] == '/'              // enter a end tag
        IF token[0] != ('/' + stack.pop)    // compare stack-popped tag and the end tag
            return false

    IF '>' AND token[0] != '/'              // push the tag into stack
        stack.push(token)
        insideTag = false
        CONTINUE

    IF insideTag: tokenBuf.append(xml[i])   // append current char to the string buffer
return stack.isEmpty()                      // the stack should be empty finally
```

```java=
foreach token t in XML
    IF t = start_tag            // Push the current XML tag 't' onto the stack
        stack.push(t)

    IF t = end_tag
        t2 = '/' + stack.pop()
        IF t2 != t              // Verify whether the current XML tag 't' matches the previous tag
            return false

return stack.isEmpty()          // Ensure that the stack is empty by the end
```
