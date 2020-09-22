# Keyboard

The original Jupiter Ace had a terrible keyboard: rubbery, but somehow even cheaper and less reliable than the ZX Spectrum (if you can believe it).

![Case](keyboard6.png)

The Minstrel4th kit has an optional keyboard made with tactile switches. It works perfectly well, but it's not fun to type on for more than a few minutes. I needed something better. Dammit, I *deserved* something better. I was determined to make the ultimate Jupiter Ace.

## Templates

The secret to making a keyboard, I found, is getting the right keyboard template designed and made. Can you imagine the effort in creating a suitable layout for a keyboard? Thankfully you don't have to - you can [use this website](http://www.keyboard-layout-editor.com/#/) or [here](http://www.keyboard-layout-editor.com/##@@_x:1&a:0%3B&=!%0A1%0A%0A%0ADel%20line&=%2F@%0A2%0A%0A%0ACaps&_a:4%3B&=%23%0A3&_a:0%3B&=$%0A4%0A%0A%0AInv%20Vid&=%25%0A5%0A%0A%0A%E2%86%90&=%2F&%0A6%0A%0A%0A%E2%86%91&=%2F&%0A7%0A%0A%0A%E2%86%93&=(%0A8%0A%0A%0A%E2%86%92&=)%0A9%0A%0A%0AGraph&=%2F_%0A0%0A%0A%0ADelete%3B&@_x:1.5&a:4%3B&=Q&=W&=E&=R%0A%3C&=T%0A%3E&=Y%0A%5B&=U%0A%5D&=I%0A%C2%A9&=O%0A%2F%3B&=P%0A%22%3B&@_x:1.75%3B&=A%0A~&=S%0A%7C&=D%0A%5C&=F%0A%5B&=G%0A%5D&=H%0A%5E&=J%0A-&=K%0A+&=L%0A%2F=&_a:6%3B&=Enter%3B&@_x:1.25&fa@:2%3B%3B&=Shift&_a:4&f:3%3B&=Z%0A%2F:&_f:3%3B&=X%0A%C2%A3&_f:3%3B&=C%0A%3F&_f:3%3B&=V%0A%2F%2F&_f:3%3B&=B%0A*&_f:3%3B&=N%0A,&_f:3%3B&=M%0A.&_a:6%3B&=Symbol%20Shift&_a:4&fa@:1&:0&:0&:0&:0&:0&:2%3B%3B&=Break%0A%0A%0A%0A%0A%0ASpace) (which is a link that might work on Chrome and go straight to my design). With this website, you can create a layout which you can then export as a series of weird strings, like this:

![Layout](keyboard1.png)

[{x:1,a:0},"!\n1\n\n\nDel line","@\n2\n\n\nCaps",{a:4},"#\n3",{a:0},"$\n4\n\n\nInv Vid","%\n5\n\n\n←","&\n6\n\n\n↑","&\n7\n\n\n↓","(\n8\n\n\n→",")\n9\n\n\nGraph","_\n0\n\n\nDelete"],
[{x:1.5,a:4},"Q","W","E","R\n<","T\n>","Y\n[","U\n]","I\n©","O\n;","P\n\""],
[{x:1.75},"A\n~","S\n|","D\n\\","F\n[","G\n]","H\n^","J\n-","K\n+","L\n=",{a:6},"Enter"],
[{x:1.25,fa:[2]},"Shift",{a:4,f:3},"Z\n:",{f:3},"X\n£",{f:3},"C\n?",{f:3},"V\n/",{f:3},"B\n*",{f:3},"N\n,",{f:3},"M\n.",{a:6,f:3},"Symbol Shift",{a:4,fa:[1,0,0,0,0,0,2]},"Break\n\n\n\n\n\nSpace"]

You can then copy this weird stuff [into this website](http://builder.swillkb.com), and the clever system will generate some outlines for you (the ones I made are in this repo). The outlines are ready for using in a laser cutter or other computer-controlled tool.

The template is nothing more than plate with holes into which you pop in the switches: they just snap into place. You then mount the plate on a base, and optionally add a top blanking plate. Designing a template like this by hand would take a long time, so this web tool is amazingly useful.

Of course, at this point you might think "hold on - maybe I can improve the original keyboard - you know, add a space bar or sensible shift keys". To this I say "Yes! Go for it!" but remember than you can't change what each specific key does, so don't get too carried away.

After than, find someone with a GlowForge or other laser cutter and make a copy of a rigid plate to hold the switches. Thin (1.5mm) acrylic just about works, but it won't be very strong. It's what I used, which is why my design includes about five extra supports to prevent sagging and bounce. 

## Switches

You will now need 40 switches (or more if you are making improvements). I ordered some [Cherry switches from Amazon](https://www.amazon.com/gp/product/B01N2L8RR2/), but there are cheaper places if you can wait for a delivery from, say, China. Make sure the switches you pick match the ones you select in the template creation tool. Different switches have different outlines.

You'll also need key caps. Sadly there are no professionally made Jupiter Ace keycaps. I know, right? I used some [clear lid clip-on keycaps](https://www.amazon.com/gp/product/B01M023NFK) (which are.. you know.. cool? Maybe? Very "1980 budget keyboards for a ZX81" anyway.) I then added a set of labels I printed on a nice color printer when no-one was looking. The bitmap I made is in the repo. I considered getting proper, blank keycaps and laser etching or dye-subliminating the labels, but then I thought, "No, don't be silly".

Now all you have to do is solder up the keys.

## Wiring the keyboard the way I did it vs. Wiring up the keyboard the sensible way

The keys are arranged in a matrix of columns and rows, although there are a few out-of-order keys to keep you on your toes. The best guide is the manual that comes with the Minstrel4th kit which does a great job of listing which switches need soldered together in which order. There's nothing fancy: no Arduino-based keyboard controller, no USB interface - these are just switches connected via wires, and then to the computer where some diodes and pull-up resistors connect it directly to the Z80.

Now, the sensible way to solder a keyboard matrix is to get a custom PCB made. This will not only replace all the wiring but provide a rigid and strong base. You should definitely do that - although it will not be very cheap and it will take a while.

The next most sensible way to solder the keys is to snap them into your template, maybe add a tiny bit of hot glue to hold them in place, and then get a long piece of single-stranded wire, lay it over the keys and solder each point, repeating the process for each row. Then cover these bare wires in something insulating (like Kapton tape), and lay the column wires over and solder them. That will result in the least possible number of solder joints, and as each joint is a potential point of failure, that's a good thing.

![Soldering](keyboard3.png)

On no account just cut up a hundred short pieces of hook-up wire and solder each switch terminal multiple times. It's madness. Don't do it. Learn from my mistake.

## Assembling

Use various spacers to combine the keyboard baseplate and the blanking plate that goes on top. Screw the enture thing to a baseplate to hold it rigidly alongside the PCB for the computer. It can look pretty sharp (as long as no-one looks at the wiring side).

![Assembly](keyboard4.png)

## Connecting the keyboard

Again, nothing subtle. The column and row wires connect directly to the computer. There's a little connector on the Minstrel4th.

## Issues

The Jupiter Ace keyboard electronics are not sophisticated, and the Minstrel4th proudly duplicates them. The matrix of switches is scanned multiple times a second by the Z80, and if the switch is closed, the row/column values will provide the software with a unique value - that's the key being pressed. There is no roll-over or buffering or anything clever, so if you make a keyboard that is too nice, you'll quickly discover the Ace can't keep up. There is no way round this without a complete rewrite of the Ace ROM and no-one wants to do that. A slight improvement can be achieved by overclocking the Ace, something with the Minstrel4th can do. With the clock at double speed, typing is a little better.

But be warned: you might spend a lot of time and effort improving the keyboard but the overall experience is strangely much the same. For long typing sessions, you are probably better off using an emulator (not that they can handle the keyboard considerably better, but at least they're free).


# Case

The original Jupiter Ace case, and I say with this great fondness, was also terrible. Thin, brittle plastic - the same used in yoghurt pots. White that would go yellow. Paper stickers of important key functions glued on. 

And yet somehow I made something worse.

![Case](keyboard2.png)

It started off ok, with a solid acrylic plastic base to attach the keyboard and the Minstrel board. Then I got cocky and tried to make the rest. Let's just say acrylic is great for 2D cuts, and anything else takes more time and talent than I have. If I had a larger 3D printer - I wouldn't use that either. 3D printed cases never look that great to me. I did consider getting a plastic vacumm formed case made, but only for a few minutes.

![Case](keyboard5.png)

The case I made has a lid that often stays in place (I need access to the reset button and jumpers). I also exposed the RC2014 connector, as I've a specially adapted backplane with some cards that help with software development. If you kind of squint, it can look OK I guess.
