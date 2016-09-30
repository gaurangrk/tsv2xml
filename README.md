# tsv2xml
Convert Android Translated strings (for localisation) from Google spreadsheets to strings.xml

This is a bash script. You can run it in linux.

If you want to contribute a DOS or MAC script, please let me know.

This script converts your translated string from XLS format to strings.xml.

INSTALLATION:

1. Clone this repository into your home directory
2. Add the cloned directory to your $PATH
3. Change perms of tsv2xml to 755

MODIFICATIONS:

1. replace $RESPATH with the path of the res folder in your project
2. make sure the values-xx folders are created, where xx is the two letter langugae code for the particular language


USAGE:
	tsvtoxml tsv_input_file xml_output [language-code]
	
	tsv_input_file: (required) should be a tab separated values file
	xml_output: (required) file should be something like strings.xml
	language_code: (optional) if present, the output file is moved to that values folder, 
			eg. if language_code is mr, the output file will be moved to res/values-mr folder


REQUIREMENTS:
1. your translated straings XLS file should have the following format

	|----------------------------------------------------------------------------------------|
	| Col1 (Name)           |   Col2 (Original String)      |   Col3 (Translated String)     |
	|----------------------------------------------------------------------------------------|
	| app_name              |   My Exciting Original App    |   My Exciting Translated App   |
	| hello_world           |   Hello Original World        |   Hello Translated World       |
	|        .              |        .                      |           .                    |
	|        .              |        .                      |           .                    |
	|        .              |        .                      |           .                    |
	|----------------------------------------------------------------------------------------|

2. Upload the XLS file to Google Spread sheets, and then download as Tab-Separated-Values

3. After conversion to strings.xml, the strings.xml would be of the format

\<?xml version="1.0" encoding="utf-8"?><br>
\<resources><br>
\<string name="app_name">My Exciting Translated App</string><br>
\<string name="hello_world">Hello Translated World</string><br>
	.<br>
	.<br>
	.<br>
\</resources><br>


SCREEN OUTPUT
	
tsv2xml will print out all the occurances of the % character, so that you can check whether String formatters like %d, %s etc are correct in the translated strings
