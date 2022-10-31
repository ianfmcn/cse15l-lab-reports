**Week 5 Lab Report** <br/>
*Researching Commands*<br/>

**Find** <br/>
*`-iname`* <br/>
Using `-iname` instead of `-name` allows us to make case insensitive searches for files, which is useful when you have files with different cases but similar characters otherwise.<br/>

![image](inamefiles.png)<br/>
![image](name.png)<br/> 
With `-name`, only test.txt is returned, but with `-iname`, all files with test are returned.<br/>
![image](iname.png)<br/>


*`-mtime`*<br/>
Using `-mtime` allows us to filter files that we've edited within a specific time range, which can be useful if we are trying to find files that we've recently edited.<br/>

![image](mtime.png)<br/>
Using +x, where x is an integer number of days, the find command returns files that were modified within that number of days. 

*`-delete`*<br/>
Using `-delete` allows us to find and delete files, and can be useful when we want to delete all files of a type or all files containing certain characters.<br/>

Files:<br/>
The files with test in their names are present.<br/>
![image](predelete.png)<br/>

Files after using delete:<br/>
The files with test were deleted and are now gone.<br/>
![image](delete.png)
![image](postdelete.png)


**Grep**<br/>
*Bracket Arguments*<br/>
Using brackets inside the search argument for `grep` can let us make make single character substitutions so that we don't have to reenter the search argument for a difference of one character.<br/>
File Contents:<br/>
![image](grep1.png)<br/>

![image](grep1result.png)<br/>
Calling `[CDR]NA` resulted lines with CNA, DNA, and RNA to be printed without having to use `grep` separately for each of the terms.<br/>

*Before and After Lines*<br/>
Using `-B` and `-A` followed by an integer number of lines allows us to print lines before and after the lines that contain the search argument. This can be useful if we want to find out more specific information within a file without having to manually open it.<br/>
(The same file from bracket arguments is being used.)<br/>
![image](grep2result2.png)<br/>
Using only `-A` returned the line with RNA and the line after.<br/>
![image](grep2result1.png)<br/>
Using `-A` and `-B` returned the line with RNA and 1 line before and after.<br/>

*Searching Multiple Strings at a Time*<br/>
Using single quotes, pipes, and backslashes, we can search for multiple strings at a time with one `grep` command. <br/>
![image](grep3result.png)<br/>
Using the argument `'DNA\|RNA\|CNA'`, I searched the grepbracket.txt file for all 3 strings at the same time, so it returned all lines that contained at least 1 of the 3 strings.<br/>


**Less**<br/>
*`-N`*<br/>
Using `-N` after `less` allows us to view a file's contents in `less` view with the line numbers included. This can be helpful when we need to browse a document and see the contents at a certain line.
![image](less1result.png)<br/>
After calling `less -N grepbracket.txt` in the terminal, line numbers appeared in the `less` view.

*Searching With Forward Slash*<br/>
Using a forward slash while in the `less` view mode highlights existing instances of the search arguments. <br/>
![image](less2result.png) <br/>
After calling `less grepbracket.txt` and typing `/a` then pressing enter while in `less` view mode, all of the "a" characters are highlighted.<br/>

*Skipping Ahead with `ESC+Space`*<br/>
Using `ESC+Space` while in the `less` view mode skips forward a screen-full of lines, even if there are no more lines left in the document. While this is not the most useful for a document with 3 lines, it would be extremely helpful if you needed to search a large document page by page.<br/>
![image](less3result.png)<br/>
After calling `less grepbracket.txt` and typing `ESC+Space`, the `less` viewer skips forward more lines than there are in the document.

