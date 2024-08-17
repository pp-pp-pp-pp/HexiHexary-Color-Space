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

part 3: ##!!HEX to #HEX
disclaimer; the language surrounded the hex color space is very convoluted, im trying my best to distinguish between hexihexary and hex color space (hexidecimal color space)

we already looked at how to convert #HEX to ##!!HEX, and infact we showed that technically no conversion is needed, since #00FFFF is equal to ##!!00FFFF.

This is indeed a great strength of HexiHexary. The tradeoff of course is that its not feasible to convert between ##!!RGB and sRGB in your head, since you need to divide and multiple by 165 and 255 respectively. However as ive just pointed out its very easy to convert from ##!!HEX or #HEX to ##!!RGB, but now we are going to look at the inverse of that which is ##!!RGB to ##!!HEX or #HEX, which is thankfully also rather simple.

we can take our example of ##!!RGB(0, 160, 160) and work out the ##!!HEX. Remember that we cant convert straight to standard #HEX, but once we convert to ##!!HEX it will be in a format that is identical to #HEX, its a little confusing to say in language so let me just show you

We know that all we have to do it find the ##!!HEX of ##!!RGB(160), since 0 will stay and the blue and green channels are the same. Remember that ##!!RGB (HexiHexary RGB) only goes from 0 to 165, if we have a value like (0, 247, 247), its probably safe to assume that this is a standard rgb value and not a ##!!RGB value. Reguardless, heres how we convert ##!!160.

We are going to be making use of the positional operator we defined earlier, the backtick followed by the tilde

it looks like this: ~

note if you try to write this in markdown you will have a bad time

160 breaks down to 

15~1 (15*10=150)

and

10~0 (10*1=10)

150+10=160, that's how we check our work

15 in #HEX and ##!!HEX is F

10 in #HEX and ##!!HEX is A

therefore ##!!RGB(0, 160, 160) = ##!!00FAFA

If you're paying close attention, you may notice something slightly strange going on

we have previously established that ##!!RGB(0, 160, 160) = sRGB (0, 247, 247)

The problem that arises is that we can prove that this method is correct

160/165=.969

247/255=.968

however, 247 decimal to hexidecmal is *F7*, *NOT* *FA*...

the solution to this is simple if a bit confusing

##!!00FAFA != #00FAFA

however

##!!00FAFA ≈ #00FAFA

we know that this is true because our answer ##!!RGB(0, 160, 160) = ##!!00FAFA is approximately close to  ##!!RGB(0, 160, 160) = ##!!RGB(0, 247, 247), and as previously stated we can prove the ##!!RGB value is "correct" with 

160/165=.969

247/255=.968

This is essentially the purpose of HexiHexary Color Space: is provides a way to convert between 2 "simulations" of Hex colors and RGB colors, referred to as HexiHexaryRGB (##!!RGB) and HexiHexary (##!!HEX). I can look at ##!!100 and in just a split second in my head convert it to ##A0, and back again. I cant do this with standard hexidecimal and standard rgb.

I can look at ##!!BE and in just a few seconds in my head convert it to ##!!125, and take a few more seconds to check my answer using hexidecimal letters without having to multiply anything by 16 or worry about remainders
B=11~1, E=14~0=110+14=##!!125

I cant do this for standard hex and standard rgb. if i want to figure out what BE is in sRGB, I have to remember a lot of stuff. a lotttt of stuff. I don't want to think about that. with Hexihexary, I don't have to.
