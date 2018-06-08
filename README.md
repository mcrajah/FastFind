# Fast Find
A sublime plugin to search/find in sublime project. 

## Features
* The plugin currently supports ripgrep (required ripgrep executabl, see ripgrep section below)
* Allows user to add search pathts to right click menu
* Shows search hits in new window with hot links
* User for define the amount of context for each serach hit
* Optimize search by setting file filters and ignore folders
* Syntax highlight for search hits
* Addition search engines will be supported later

## Requirement
* Ripgrep executable
* Sublime Text 3 +
* Not tested in Sublime Text 2

## Installation
Clone the repo or download zip. The files need to under a folder (ex: FastFind) under the sublime plugsins folder
Copy the contents of the User directory to sublime plugins user directory. If you already have customer actions for mouse click defined in ```Default (Windows0.sublime-mousemap``` then merge the contents. If you are not on windows, then update your corresponding OS specific mouse map.

## Usage
* Once installed, the plugin will work only if files are saved under a project and if the project is open
* Right click will add a Fast Find option if the plugin is loaded by Sublime Text
* You can added multiple seach folders for large projects to optimize FastFind using the ```Fast Find > Add new seach location``` option
* Open settings file using the ```Fast Find > Settings``` option
* Each search opens a new view in sublime text, double click the seach to jump to location in project file
* All open Fast Find views can be closed using the ```Fast Find > Close all Fast Find Tabs```

## Setttings File
Below is an example settings file
```
{
	"FastFindSublime_file_type_pattern":
	[
		"c",
		"cpp",
		"sh",
		"make"
	],
	"FastFindSublime_non_std_file_type_pattern":
	[
		"x",
		"s",
		"scons",
		"api",
	],
	"FastFindSublime_ignore_folders":
	[
  ".git",
	],
	"FastFindSublime_prompt_before_searching": false,
	"FastFindSublime_executable": "rg",
	"FastFindSublime_before_context":1,
	"FastFindSublime_after_context":1,
	"FastFindSublime_display_outline": true,
}
```
### Settings file explained
* ```FastFindSublime_file_type_pattern``` : List standard file patterns here
* ```FastFindSublime_non_std_file_type_pattern```: List non-standard file patterns here
* ```FastFindSublime_ignore_folders```: List ignore folders here
* ```FastFindSublime_prompt_before_searching```: Not supported yet
* ```FastFindSublime_executable```: path to ripgrep executable, if in system path, just name of executable, else full path
* ```FastFindSublime_before_context```: Number of lines of context before hit
* ```FastFindSublime_after_context```: Number of lines of context after hit
* ```FastFindSublime_display_outline```: Draw outline around search keywords
## RipGrep
RipGrep executable and project details can be found at https://github.com/BurntSushi/ripgrep
