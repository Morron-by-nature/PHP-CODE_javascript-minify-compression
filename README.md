java-minify
===========

//Javascript minify script simple code!!
<?PHP
//START Remove comments.
$buffer = str_replace('/// ', '///', $buffer);		
$buffer = str_replace(',//', ', //', $buffer);
$buffer = str_replace('{//', '{ //', $buffer);
$buffer = str_replace('}//', '} //', $buffer);
$buffer = str_replace('*//*', '*/  /*', $buffer);
$buffer = str_replace('/**/', '/*  */', $buffer);
$buffer = str_replace('*///', '*/ //', $buffer);
$buffer = preg_replace("/\/\/.*\n\/\/.*\n/", "", $buffer);
$buffer = preg_replace("/\s\/\/\".*/", "", $buffer);
$buffer = preg_replace("/\/\/\n/", "\n", $buffer);
$buffer = preg_replace("/\/\/\s.*.\n/", "\n  \n", $buffer);
$buffer = preg_replace('/\/\/w[^w].*/', '', $buffer);
$buffer = preg_replace('/\/\/s[^s].*/', '', $buffer);
$buffer = preg_replace('/\/\/\*\*\*.*/', '', $buffer);
$buffer = preg_replace('/\/\/\*\s\*\s\*.*/', '', $buffer);
$buffer = preg_replace('/[^\*]\/\/[*].*/', '', $buffer);
$buffer = preg_replace('/([;])\/\/.*/', '$1', $buffer);
$buffer = preg_replace('/((\r)|(\n)|(\R)|([^0]1)|([^\"]\s*\-))(\/\/)(.*)/', '$1', $buffer);
$buffer = preg_replace("/([^\*])[\/]+\/\*.*[^a-zA-Z0-9\s\-=+\|!@#$%^&()`~\[\]{};:\'\",<.>?]/", "$1", $buffer);
$buffer = preg_replace("/\/\*/", "\n/*dddpp", $buffer);
$buffer = preg_replace('/((\{\s*|:\s*)[\"\']\s*)(([^\{\};\"\']*)dddpp)/','$1$4', $buffer);
$buffer = preg_replace("/\*\//", "xxxpp*/\n", $buffer);
$buffer = preg_replace('/((\{\s*|:\s*|\[\s*)[\"\']\s*)(([^\};\"\']*)xxxpp)/','$1$4', $buffer);
$buffer = preg_replace('/([\"\'])\s*\/\*/', '$1/*', $buffer);
$buffer = preg_replace('/(\n)[^\'"]?\/\*dddpp.*?xxxpp\*\//s', '', $buffer);
$buffer = preg_replace('/\n\/\*dddpp([^\s]*)/', '$1', $buffer);
$buffer = preg_replace('/xxxpp\*\/\n([^\s]*)/', '*/$1', $buffer);
$buffer = preg_replace('/xxxpp\*\/\n([\"])/', '$1', $buffer);
$buffer = preg_replace('/(\*)\n*\s*(\/\*)\s*/', '$1$2$3', $buffer);
$buffer = preg_replace('/(\*\/)\s*(\")/', '$1$2', $buffer);
$buffer = preg_replace('/\/\*dddpp(\s*)/', '/*', $buffer);
$buffer = preg_replace('/\n\s*\n/', "\n", $buffer);
$buffer = preg_replace("/(<!--.*-->)/Us","$1QQXQQ", $buffer);
do {$buffer = preg_replace("/(\(\s*[\"]\s*[^\(\)\"]*<!--.*-->)QQXQQ/Us","$1", $buffer, 1, $count);} while ($count);
do {$buffer = preg_replace("/(\(\s*[\']\s*[^\(\)\']*<!--.*-->)QQXQQ/Us","$1", $buffer, 1, $count);} while ($count);
$buffer = preg_replace("/(<!--.*-->QQXQQ)/Us","", $buffer);
$buffer = preg_replace('/([^\n\w\-=+\|!@#$%^&*()`~\[\]{};:\'",<.>\/?\\\\])(\/\/)(.*)/', '$1', $buffer);
//END Remove comments.	
//START Remove all whitespaces
$buffer = preg_replace('/\s+/', ' ', $buffer);
$buffer = preg_replace('/\s*(?:(?=[=\-\+\|%&\*\)\[\]\{\};:\,\.\<\>\!\@\#\^`~]))/', '', $buffer);
$buffer = preg_replace('/(?:(?<=[=\-\+\|%&\*\)\[\]\{\};:\,\.\<\>\?\!\@\#\^`~]))\s*/', '', $buffer);
$buffer = preg_replace('/([^a-zA-Z0-9\s\-=+\|!@#$%^&*()`~\[\]{};:\'",<.>\/?])\s+([^a-zA-Z0-9\s\-=+\|!@#$%^&*()`~\[\]{};:\'",<.>\/?])/', '$1$2', $buffer);
//END Remove all whitespaces

alternative Option TWO shorter:
//START Remove comments.
$buffer = str_replace('/// ', '///', $buffer);		
$buffer = str_replace(',//', ', //', $buffer);
$buffer = str_replace('{//', '{ //', $buffer);
$buffer = str_replace('}//', '} //', $buffer);
$buffer = str_replace('*//*', '*/  /*', $buffer);
$buffer = str_replace('/**/', '/*  */', $buffer);
$buffer = str_replace('*///', '*/ //', $buffer);
$buffer = preg_replace("/\/\/.*\n\/\/.*\n/", "", $buffer);
$buffer = preg_replace("/\s\/\/\".*/", "", $buffer);
$buffer = preg_replace("/\/\/\n/", "\n", $buffer);
$buffer = preg_replace("/\/\/\s.*.\n/", "\n  \n", $buffer);
$buffer = preg_replace('/\/\/w[^w].*/', '', $buffer);
$buffer = preg_replace('/\/\/s[^s].*/', '', $buffer);
$buffer = preg_replace('/\/\/\*\*\*.*/', '', $buffer);
$buffer = preg_replace('/\/\/\*\s\*\s\*.*/', '', $buffer);
$buffer = preg_replace('/[^\*]\/\/[*].*/', '', $buffer);
$buffer = preg_replace('/([;])\/\/.*/', '$1', $buffer);
$buffer = preg_replace('/((\r)|(\n)|(\R)|([^0]1)|([^\"]\s*\-))(\/\/)(.*)/', '$1', $buffer);
$buffer = preg_replace("/([^\*])[\/]+\/\*.*[^a-zA-Z0-9\s\-=+\|!@#$%^&()`~\[\]{};:\'\",<.>?]/", "$1", $buffer);
$buffer = preg_replace("/\/\*/", "\n/*dddpp", $buffer);
$buffer = preg_replace('/((\{\s*|:\s*)[\"\']\s*)(([^\{\};\"\']*)dddpp)/','$1$4', $buffer);
$buffer = preg_replace("/\*\//", "xxxpp*/\n", $buffer);
$buffer = preg_replace('/((\{\s*|:\s*|\[\s*)[\"\']\s*)(([^\};\"\']*)xxxpp)/','$1$4', $buffer);
$buffer = preg_replace('/([\"\'])\s*\/\*/', '$1/*', $buffer);
$buffer = preg_replace('/(\n)[^\'"]?\/\*dddpp.*?xxxpp\*\//s', '', $buffer);
$buffer = preg_replace('/\n\/\*dddpp([^\s]*)/', '$1', $buffer);
$buffer = preg_replace('/xxxpp\*\/\n([^\s]*)/', '*/$1', $buffer);
$buffer = preg_replace('/xxxpp\*\/\n([\"])/', '$1', $buffer);
$buffer = preg_replace('/(\*)\n*\s*(\/\*)\s*/', '$1$2$3', $buffer);
$buffer = preg_replace('/(\*\/)\s*(\")/', '$1$2', $buffer);
$buffer = preg_replace('/\/\*dddpp(\s*)/', '/*', $buffer);
$buffer = preg_replace('/\n\s*\n/', "\n", $buffer);
$buffer = preg_replace("/([^\'\"]\s*)<!--.*-->(?!(<\/div>)).*/","$1", $buffer);
$buffer = preg_replace('/([^\n\w\-=+\|!@#$%^&*()`~\[\]{};:\'",<.>\/?\\\\])(\/\/)(.*)/', '$1', $buffer);
//END Remove comments.	
//START Remove all whitespaces
$buffer = preg_replace('/\s+/', ' ', $buffer);
$buffer = preg_replace('/\s*(?:(?=[=\-\+\|%&\*\)\[\]\{\};:\,\.\<\>\!\@\#\^`~]))/', '', $buffer);
$buffer = preg_replace('/(?:(?<=[=\-\+\|%&\*\)\[\]\{\};:\,\.\<\>\?\!\@\#\^`~]))\s*/', '', $buffer);
$buffer = preg_replace('/([^a-zA-Z0-9\s\-=+\|!@#$%^&*()`~\[\]{};:\'",<.>\/?])\s+([^a-zA-Z0-9\s\-=+\|!@#$%^&*()`~\[\]{};:\'",<.>\/?])/', '$1$2', $buffer);
//END Remove all whitespaces
