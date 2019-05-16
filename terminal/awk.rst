awk 基本用法::
	
	ls -al | awk {print $0"OwO"}
	ls -al | awk test.awk

check version::
	
	awk --version

Printing Column or Field::

	awk '{print $3 "\t" $4}' marks.txt

Printing All Lines::
	
	awk '/a/ {print $0}' marks.txt
	
	#print 有'a'的那一行

Counting and Printing Matched Pattern::
	
	awk '/a/{++cnt} END {print "Count ", cnt}' marks.txt

::

	#!/bin/csh -f
	awk '\
	BEGIN { print "BEGIN"}  \
		{ print $3 } \ 
	END { print "END"} \



To find names of other environment variables, use 'env' command::

	awk 'BEGIN { print ENVIRON["USER"]}'


represents the current file name::
	
	awk 'END {print FILENAME}' filename

ignore case::

	awk 'BEGIN {IGNORECASE = 1} /amit/' marks.txt

::

	ls -al | sh test.sh
	ls -al | sh test.awk



SA hw1::

 ls -lAR | sort -hk 5,5 -r | awk '{ if( NR< 6) print NR "\t" $5 "\t" $9 } '





