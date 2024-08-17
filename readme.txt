developers note: this format does not play well with markdown due to its use of backtick [`] and tilde [~], im looking into this but for now im just writing this readme in txt format

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

`~1 is tens place

`~2 is hundreds place, and so on and so fourth

F~1 + F~0

F~1 = 15*10=150 (as previously discussed using `~ to denote positional information)

F~0 = 15*1=15

Thus FF = 165

Therefore we can say 0xFF = ##!!165 (we can use '##!!' similarly to how we use 0x to show hexidecimal, ##!! meaning "double hex" (reference to how # denotes a hex color- ##!! meansa double hex)

therefore the final answer would be 

#00FFFF = ##!!00FFFF

notice something? this system truly is compatible with hex and srgb, we dont need to change the code at all technically, but we *can* show it in srgb format for clarity

#00FFFF = ##!!RGB(000, 165, 165)

part 2: converting from sRGB() and from Hex# to DoubleHex##!!

Lets take our example cyan and start with sRGB instead of Hex

Cyan in sRGB = (0, 255, 255)
to convert sRGB to HexiHexaryRGB aka ##!!RGB we can divide each channel by 255 then multiply by 165
luckily this example is super easy
255/255=1*165=165
answer: sRGB (0, 255, 255) to ##!!RGB = (0, 165, 165)

we can do the same backwards to convert from ##!!RGB to sRGB, we can use a slightly more complex example of ##!!RGB (if you notice, !!## is a clever way of showing that this is 'not' rgb (!=not; anyways) ##!!RGB (0, 160, 160) to sRGB = divide all by 165 then multiply by 255

 this gets us 0.969696969697*255=247.27 which rounds to 247 which seems like it would make sense
160/165=.969
247/255=.968
close enough.
answer: ##!!RGB (0, 165, 165) to sRGB = sRGB (0, 247, 247)
