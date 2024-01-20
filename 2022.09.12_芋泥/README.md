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
