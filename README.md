# Macro SD (a.k.a. SDXL) Drive

Do you think SD Cards are too small? Do you long for the times of big, beautiful labels on cartridges which have amazing 
feel in your hand? Then you've come to the right place. This is the repository for Macro SD cards - a convoluted system
to create cool cartridges for your games, movies, or whatever else.

If you'd like to see these cards in action, check out my [full length video](https://www.youtube.com/watch?v=YsOAE5c7YXs) on the original console which uses these.

[![I designed a console that's already obsolete video](https://img.youtube.com/vi/YsOAE5c7YXs/0.jpg)](https://www.youtube.com/watch?v=YsOAE5c7YXs)

# Instructions

As usual, please read all instructions before beginning your project.

## Before you Begin
To assemble your own Macro SD drive you'll need the parts for at least one cartridge...

* 1x Cartridge PCBs
* 1x Cartridge Acrylic Front
* 1x Cartridge Acrylic Middle
* 4x 3m screws (preferably nylon, from [my shop](), to avoid stripping the threads or scratching your drive)

Then for the drive itself you'll need...

* 10x 3in 26 awg Silicone Wire (I like [this wire](https://amzn.to/3sZRBDP))
* Micro SD breakout ([My Shop]() or [PCBWay](https://www.pcbway.com/project/shareproject/MicroSD_breakout_board.html))
* Edge Connector ([My Shop]() or [Digikey](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/5-5530843-4/770549?s=N4IgTCBcDaIIIGYCMB2MCC0A5AIiAugL5A))
* Micro SD card reader ([My Shop]() or [Amazon](https://amzn.to/458Vaox))
* USB Extension Cable (for standalone version, [find the length / connector style you need based on your SD reader](https://amzn.to/455YUax). This acts as the cable which comes out the back of the drive)
* 4x Rubber feet (optional, but recommended for standalone drive from [My Shop]() or [Amazon](https://amzn.to/45WZjNI))
* Arduino-Compatible board (optional, I use a [Seeed Studio XIAO](https://amzn.to/3EPvCSU) because it's tiny)

> The easiest (and probably cheapest) way to get all these components without forgetting anything is to pickup a [Macro SD Drive Bay Stater Kit](https://abe.today/products/drive-bay-starter-kit) 
> from my shop, which includes all drive bay components (except the Arduino) and 3 cartridges worth of parts! 
> 
> You're obviously welcome to order parts from wherever but custom parts like acrylic, PCBs, etc. all have setup costs which means low-volume orders get very expensive per unit. 
> Similarly, even things like rubber feet are only really sold in bulk, so if you order from me I can supply exactly what you need for the project at a better rate because I've
> imported everything in bulk.
> 
> Plus it helps supports the project and my [Youtube channel](https://www.youtube.com/channel/UCUxIu91gGsK9Q0tTcQM8iNw).


Aside from consumable components, you'll also need the following tools...

* 3D Printer (I use a [Flashforge Adventurer 3](https://amzn.to/462LQEf))
* Soldering Iron (I use a battery powered [Ryobi Soldering Iron](https://amzn.to/46nRMHM))
* Screw Driver (I use an off-brand [Blue Ridge Screw Driver Set](https://amzn.to/3EVlQ1n))
* SD Cards (one per cart, you can find decent bundles [on amazon](https://amzn.to/462Mul9) but if you're making a lot of carts you'll likely have better deals on Aliexpress, etc.)

Optionally, you may also want...

* Hole Tap (I use this [generic T-handle rachet tap](https://amzn.to/3Rqd7fk), it's not the best but it works)
* Photo Printer for Cart Labels (I use a [Polaroid Hi-print](https://amzn.to/3Zv5lTx))
* Hot Glue Gun (I use a [Ryobi Hot Glue gun](https://amzn.to/3LycUmo))
* Soldering Mat (I use a [Generic Silicone mat](https://amzn.to/3ZsERlk))
* Flush Cutters (I use a [Hakko-CHP-170](https://amzn.to/3LzG4Sp))

Please note all links above are affiliate links which help support my Youtube channel and future  projects.

## Step 1. Picking your Drive Style

This repo has a few drive options to pick from depending on your needs.

### Drive Type: Standalone or Internal

A **standalone** drive is one which can sit on a desk and use Macro SD cards like a normal SD card reader. You can plug it into any compatible computer
and it's most useful for writing cards to be consumed on another device. This version is made up of at least a top and bottom piece.

An **internal** drive is one which is designed to be mounted inside a device like the [game.work](https://github.com/abeisgoat/game.work). It has flaired
edges with screw holes which allow it to be screw from the top downwards onto a frame. It also lacks a bottom so the wires can route
out into the rest of the device.

> Note: I recommend making a standalone drive first as it's more self-contained and will help you understand the whole device before integrating with a project.

### Drive Length: 127mm or 107mm

The original drive in the [game.work](https://github.com/abeisgoat/game.work) is a 127mm drive bay. As you can see above
in the video thumbnail, when a cartridge is inserted, the edge of the cart is flush with the edge of the bay. This provides
a sleek look, but fresh female edge connectors can be very tight and without a good grip it can be difficult to remove
the cartridge without hurting the paint job of the bay.

The alternative is to use the 107mm drive which leaves 20mm of overhang to more easily grab the cart to pull it out. This
version is also quicker to print as it uses less material.

> Note: I recommend starting with the 107mm variant to reduce printing time.

### Connector Type: Full or Half

As mentioned in the length section, edge connectors are designed to be snug so to improve control over the snugness
I've designed a "half" connector variant where the edge connector (which normally has contacts on both the top and bottom)
is cut in half (physically, by hand) and we only use one side along with a 3D printed bracket which we can tweak
to get the perfect tightness when inserting / removing a cart.

The full style connector is easier, but it **will** be snug. The half style connector is harder to get right, but
feels more premium in the end.

> Note: I recommend using the full style connector for your first build, then half connectors once you know what
> you're doing.

## Step 2. Printing your STLs

In the [stls](stls) folder, we have many 3D models for the combinations of options. The naming scheme is...

```
(LENGTH)mm_bay_(DRIVE TYPE)_(CONNECTOR TYPE)_part_(NUMBER)_of_(NUMBER).stl
```

Once you've determined which models you need (which will be 1-3 STLs depending on options), then you can print them.

The bottom pieces should be printed laying flat on the bed, the tops are likely best printed standing vertically with the
large opening on the bottom. You may need supports depending on your printer. Then the bracket (if used) can be printed
vertically as well.

On my printer it takes about 12hrs to print all pieces for a drive.

## Step 3. Wiring

While your models print, you can begin the soldering of components. In this step you'll need your soldering station,
the Micro SD breakout board, edge connector, your 10 wires and an optimistic attitude.

If you examine a cartridge PCB, you may notice it only has gold contact on the top, so we need to wire our edge
connector to make contact with ten of those contacts. Although the PCB has 12 pins total, we only use the ten on the
left and the two on the right.

If you insert the cart into the edge connector and look from the top down (with the cart word "UP" readable to you) the
pins are as follows...

```
VCC - DAT2 - DAT3 - CMD - CLK - GND - DAT0 - DAT1 ----------------------- SW0 - SW1
```

If you examine the Micro SD breakout board, you'll see both sides have names which match the 8 names on the left pins. 
It is your choice whether you solder to the through-holes or the pads, just make sure not to short wires to adjacent contacts.

If you're using the half connector style drive, I recommend cutting the your connector in half before soldering. I did
this carefully with a utility knife, but I'm sure there's better tools. Just cut the connectors short ends right down the middle
until you have two seperated halves. Then pick a half and wire it normally.

### (Optional) Using the SW0/SW1 Pins
For the `SW0` and `SW1` these pins are optionally used to detect when a cart is inserted into the drive. We can use an Arduino
to detect when one of these pins are pulled low (to ground).

```c
const int SW0Pin = 3;

void setup() {
  Serial.begin(9600);
  pinMode(SW0Pin, INPUT_PULLUP);
}

void loop() {
  int detState = digitalRead(SW0Pin);

  if (buttonState == LOW) {
    Serial.write(1)
  } else {
    Serial.write(0)
  }
}
```

This is helpful because it can take an operating system a few seconds to detect a cartridge, mount the volume, then
run it's contents. It's helpful to know as soon as the cart makes physical contact so we can change status LEDs on the
drive / console.

## Step 4. Assemble your Cartridges

Cartridges are easy to assemble, but the SD card slot may prove a little tricky. If you're holding the PCB in your
hand so that the word "UP" is readable, then you need to push up on the metal SD card slot to release it's latch. Then
you can insert your Micro SD (metal contact side facing you), then flip it up and slide the latch back down. If you're
confused, just fiddle with it for a moment. 

This type of latch is a little bit of a pain but is much less likely to come lose if the cart is dropped.

After your Micro SD is inserted, you'll want to take one middle layer of acrylic (the one with the square hole) and one
top layer (the non-hole one) and stack them over the SD card. If your acrylic pieces still have protective paper, you
should remove that now, but keep in mind it can be helpful to keep the paper on the top piece since it can be written
on with a sharpie if you haven't made printed labels yet (or don't intend to).

If you order the acrylic from my shop, it will come pre-threaded. Make sure you stack the pieces with the "in" side facing
the SD card (e.g. in). The rotational orientation does not matter.

If you did not order your acrylic pieces from my shop, you'll need to tap the screw holes so the nylon screws can attach.

While carefully holding your pieces in alignment, screw your screws through the layers. **Do not over tighten**, although
these will hold well, acrylic threads are easily stripped.

If you do strip the threads (that is, the screw now turns without grabbing onto anything) then just put a dab of hot glue
into the hole and squeeze your screw into that, it'll hold fine. If it doesn't hole fine, just fill the entire empty
section of the middle area with hot glue. Then it will hold fine.

## Step 5: Testing your Drive

Beyond putting anything into your 3D prints you should test and make sure you haven't made any mistakes in your soldering. 
You should have a functional Macro SD card reader and can test this by plugging a cart (with an SD card) 
into the edge connector while the SD breakout board is inserted into an SD card reader. This should show up like a normal
flash storage device on your computer.

If nothing shows up, test your SD card reader with another card, verify your wiring, look for shorts and re-check
everything else.

## Step 6. Drive Assembly

At this point the assembly will vary slightly depending on which drive style you chose. 

If you're using the full connector style, you just need to jam the edge connector between the card slot and the triagular
support. This will likely be a press-fit, but you can always add a hit of hot glue for additional support.

You'll notice that the edge connector has unused pins which hit the triangular support. This is where the [flush cutters](https://amzn.to/3LzG4Sp) 
come in. You can use these to snip off those extra pins. If you do not have cutters like these, you can probably just snap
them off with pliars, just be careful not to damage the black plastic too much.

If you're using the half connector style, use the additionally 3D printed bracket to hold the half connector in place
then screw it into the top half of the drive bay.

Once your connector is in place, you should have the Micro SD breakout board hanging there. Take your Micro SD
reader, insert the breakout into it and either place this into the standalone version's base or decide how to mount
it if you're using the internal version.

If you're using the standalone version, you can attach the Micro SD reader to your USB extension cable and run that
out the hole in the drive's back. Then screw the top and bottom together and boom, Macro SD drive.

## Step 7. Done!

You should be done and ready to take the world by storm!!

## Troubleshooting

If you need additional help, feel free to file an issue on this repo with your concerns.