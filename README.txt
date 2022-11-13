Fn11.g4b v0.3 (20221113), by deomsh - slight variation of steve6375's approach
Function: Same as  'call Fn.11' (but %@retval% can not be used)
Output: 'result=1' if FIND is found in STRING, 'result=0' if not found. For 'bad' STRING: 'message=STRING: baddbq', for bad FIND 'message=FIND: baddbq', for failed verify 'message=VERIFY: failed'
Use: Fn11.g4b [/i|/cat|cati] ["]FIND["] ["]STRING["]
Remark1: Switch '/i' for case-insensitive FIND in STRING (not usable with \Xuuuu UTF-codes!), '/cat' to FIND max 16 char(s) in STRING directly with 'cat' and '/cati' for using 'cat' with 'locatei'
Remark2: STRING is second argument on command-line, FIND comes always first. If argument can contain spaces or '=', use double-quotes around
Remark3: Double-qoute char in STRING will be found using \x22, as in original Fn.11 call. Char \x00 will not exist in STRING, but if containing textual '\x00' still found with FIND: '\x00'
Remark4: Reserved ASCII-codes: '\x0F' and '\x11', but if in STRING replaced with available 'higher' ASCII-codes (only odd numbers, up to \xFF)
Remark5: If using Fn11.g4b in a script and if FIND and STRING can maybe not be redirected, do not use '&;' (or '&&') after a line containing '[call ]Fn11.g4b
Remark6: If FIND contains spaces near ' " ' or '\x22' use instead of spaces always '\x20'. Use for '%' '\x25', for ' | ' ' \x7C ' or '\x20|\x20'
Remark7: With switch '/cat[i]': for textual '\xASCII-code' use '\\xASCII-code'. To find escaped space '\ ' use '\\ ', '\\\x20', '\x5C ' or '\x5C\x20'
Help:    Fn11.g4b (without arguments) or Fn11.g4b /? will echo text above

* Approach of steve6375 can be found on reboot.pro: http://reboot.pro/index.php?showtopic=22668#entry221888

Script is ready for use as sub-routine, just replace '!BAT' on first line for a label, for instance ':Fn11' (without quotes)

History:
v0.3
First published version
