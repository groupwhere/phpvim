# PHP Indent file for Vim (php.vim)

## Overview
This was the original vim php indent file written in 2002 and included in Vim 6.X releases.  It still works with the latest 9.X release.

Indents after <?php tag, <? tag (optional), ( )or { }.  The script can also format switch/case statements and more recently will automatically format /* comment sections */


NOTE: 1.4 adds experimental formatting (or rather, not formatting) of heredoc.

See the CHANGELOG or the script itself for more information

Comment sections are automatically formatted, adding the * on a new line until closure by */ :

```php
/* Comment line 1
 * Line 2
 */
```

Comments done using # also receive a new line with the # prepended.  But, you will have to end it manually since there is no difference between lines and the end of such sections.

Comments done using // also receive a new line with the // prepended.  But, you will have to end it manually since there is no difference between lines and the end of such sections.

It was not designed to and will not handle if blocks etc. without brackets and also does not format html.  Please use braces and separate display logic for more readable code.

## Installation
Place in your /usr/share/vim/vim8X/indent directory (e.g. /usr/share/vim/vim81/indent), replacing the version which is installed by default.

NOTE: This script is no longer included in Vim as of 7.0, yet was replaced by another script.  After many years I still use this one with Vim 7.X and 8.X because it handles tab indentation correctly without adding spaces, etc.  The current official script seems to favor the use of spaces and if you want to always start with a tab you will have to enter that yourself on a new line after a closing bracket.  You're welcome to submit ideas for improvement.

## Options
  These can optionally be added to your vimrc:

    - php_noindent_switch -- do not try to indent switch/case statements or comments (version 0.1 behavior)
    - php_indent_shortopentags -- indent after short php open tags, too
    - php_no_autocomment  -- do not automatically format comment sections
    - php_indent_space -- Use spaces instead of tabs [ This may work already if you have expandtab set in your config. ]

## Sample

Example of automatically indented code using this indent script.  All leading whitespace is tab below:
```php
	$var = array(
		'one' => 1,
		'two' => 2
	);
	/* Comment section
	 * line two
	 */

	// more code here
	function test($var)
	{
		print_r($var);
	}

	switch($argv[1])
	{
		case 'a':
			echo "A!\n";
			break;
		case 'b':
			echo "B!\n";
			break;
		default:
			echo "No!\n";
	}
```


