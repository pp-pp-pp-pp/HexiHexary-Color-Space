heres how the color space works

example conversion from HEXSRGB to 'hexihexary' , potential nicknames could be 2HEX, DoubleHex, Hexary, HEXIA, reguardless, heres how it works

HexRGB color = #00FFFF

Hex_to_HexIA = 

seperate channels

00;FF;FF

00 remains 00

FF is broken down

I need to take a moment to explain how this breakdown works, becuase it uses a new operator that looks like this '`~'

'`~' represents positional information

`~0 is ones place

\`~1 is tens place

\`~2 is hundreds place, and so on and so fourth

F\~1 + F~0

F~1 = 15*10=150 (as previously discussed using `~ to denote positional information)

F~0 = 15*1=15

Thus FF = 165

Therefore we can say 0xFF = ##!!165 (we can use '##!!' similarly to how we use 0x to show hexidecimal, ##!! meaning "double hex" (reference to how # denotes a hex color- ##!! meansa double hex)

therefore the final answer would be 

#00FFFF = ##!!00FFFF

notice something? this system truly is compatible with hex and srgb, we dont need to change the code at all technically, but we *can* show it in srgb format for clarity

#00FFFF = ##!!RGB(000, 165, 165)
