# FAAFormatter

The attached document is a .csv (comma separated variable) document but it is pipe delimited (rather than comma).

This is a Federal Aviation Administration (FAA) specification. 

There are some problems with the file that is delivered. 

*Make an program that allows a user to navigate and open a file.
*verify that the first line of the file matches the header in the file attached. otherwise msg wrong file content and quit.
*once the file content is validated, validate the values as described below.
* track the line number of any line changed in the file.
*create a .csv file with the original filename followed by -UPDATED.csv.
*create a .txt file with the original filename followed by -Changes.txt
*write line by line from the old file to the new file with existing lines or updated lines
*in the -Changes.txt file, write the line number of any line changed and write what was changed. something like 
32 PFPNF blank 
1067 CrewID PIC added
1223 CrewID SIC added
999 SimID was Classroom-changed to 1117

Details below

The first line is the header line showing what each data element is.

The 6th item is PFPNF. This column should only contain PF or PM. Sometimes it is blank.Verify that the column only contains PF or PM. Don't change it if it is blank or if something else is there. Just write out the line number to the -Changes.txt file with PFPNF blank

The 9th item in is CrewID. Some of the crew IDs are incorrect but very easy to fix programmatically. 

Crew IDs have 3 possible formats - 
First, the letter P followed by 6 digits then a space and then the letter S followed by 6 digits. See the example below.
P123456 S123456

Second, the letter P followed by 6 digits, a space and then the letters SIC
P123456 SIC

Third, the letters PIC followed by a space and then the letter S followed by 6 digits
PIC S123456

So, some records only have P123456 and needs spaceSIC appended.

Some records only have S123456 and needs PICspace prepended.

Moving on over, SimID should always be a four digit number. If it is anything else, it should be changed to 1117

