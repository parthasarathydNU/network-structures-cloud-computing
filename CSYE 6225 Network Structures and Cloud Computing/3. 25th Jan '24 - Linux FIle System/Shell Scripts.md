<-- vback to [[3. 25th Jan '24 Thursday#Shell Scripts]]

### Redirecting Standard Output and Standard Error to One File

- It is a best practice to usually redirecting both standard out and standard error to one file. 
`/dev/null` is used for disposing unwanted output, it is sometimes referred to as a "black hole"
- `ls > /dev/null 2>&1`

### Debugging on the server
- Debugging doesn't mean something is wrong - it only means that we are looking at whats happening and is part of the development process. 
- `cat` is a useful command it is used for concatenating files in to one / read the contents of a file
