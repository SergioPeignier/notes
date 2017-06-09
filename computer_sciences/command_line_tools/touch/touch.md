# Change file creation and modification dates (MacOSx)
## Touch command:
The following command should set the modification date of the file README.txt to the 11 of octobre (10) of 2016 11h50 and 2 seconds. [[CC]YY]MMDDhhmm[.ss]
 
`touch -t 201610111150.02 README.txt`

[touch](http://www.computerhope.com/unix/utouch.htm)


## SetFile command:
In order to change the creation date we need to use SetFile:

`SetFile -d '12/31/1999 23:59:59' README.txt`

[SetFile](http://apple.stackexchange.com/questions/99536/changing-creation-date-of-a-file)

## GetFileInfo command:
If you want to obtain the creation and mofification dates, you can use the GetFileInfo command:

`GetFileInfo diabetes.arff`
