# Fn11.g4b
Grub4dos script, replacement for 'call Fn.11' (find chars in string)
First published version

Fn11.g4b v0.3 (20221110), by deomsh - slight variation of steve6375's approach*
Function: Same as  'call Fn.11' (but %@^retval% can not be used)
Output: 'result=1' if FIND is found in STRING, 'result=0' if not found. For 'bad' STRING: 'message=STRING: baddbq', for bad FIND 'message=FIND: baddbq', for failed verify 'message=VERIFY: failed'
Use: Fn11.g4b [/i] ["]FIND["] ["]STRING["]
Remark1: Switch '/i' for case-insensitive FIND in STRING (not usable with \Xuuuu UTF-codes!)
Remark2: STRING is second argument on command-line, FIND comes always first. If argument can contain spaces or '=', use double-quotes around
Remark3: Double-qoute char in STRING will be found using \x22, as in original Fn.11 call. Char \x00 will not exist in STRING, but textual no problem with FIND: '\\x00'
Remark4: Reserved ASCII-codes: '\\x7F' and '\\xFF', but if in STRING replaced with '\\x01'-'\\x1F' (odd for '\\x7F', even for '\\xFF')
Remark5: If using Fn11.g4b in a script and if FIND and STRING can maybe not be redirected, do not use '&;' (or '&&') after a line containing '[call ]Fn11.g4b
Remark6: If FIND contains spaces near ' " ' or '\x22' use instead of spaces always '\x20'. Use for '\x25' '\\x25', for ' | ' ' \\x7C ' or '\\x20|\\x20'
Remark7: CHEAT by unlocking lines preceded by #LOCKED# to FIND max 16 char(s) in STRING directly with '\x7Fchar(s)'; for instance escape-backslash with char(s) behind, use: '\x7F\char(s)' or '\x7F\x5Cchar(s)' - BTW first '\x7F'-part is not searched

Script is ready for use as sub-routine, just replace '!BAT' on first line for a label, for instance ':Fn11' (without qoutes)

* Approach of steve6375 can be found on reboot.pro: http://reboot.pro/index.php?showtopic=22668#entry221888
