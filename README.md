# park-evan-portfolio
Honors Engineering/CS Portfolio – 2025-2026

## Pen Turning

We were given a pen kit, We were tasked with using a lathe to turn a chosen piece of wood so that we could assemble the pen utilizing that wood.

We used a bandsaw to cut the piece of wood that we chose so that they would be perfect size for our pen, we made sure that the length of the wood was the same length as the brass piece that is the base for the pen. Since I wanted a two colored piece, I decided to cut two different wood pieces half the size of the brass piece and glue them together.

![](/images/pen_turning/IMG_0032.jpg)

We then utilized the Jet Mini Lathe to drill a hole into the wood. This machine spun the wood incredibly fast while you manually insert a drill into the wood to drill a hole. the speed is the how fast the wood turns and the feed is how much of the drill we put into the wood.

![](/images/pen_turning/IMG_0035.jpg)

After this we sanded our pieces to increase surface area and the glued them into the hole using super glue.

![](/images/pen_turning/IMG_0037.jpg)

After gluing our pieces into the wood, we put the wood pieces on the wood turner. The woodturner allowed us to shape the wood down to a size that would be manageable on our pen. When putting the wood pieces on, we put bearings on each end of the wood and a metal piece to keep the wood in place. We then used a square shaped pen turning tool to get the majority of the wood down and a circle shaped pen turning tool to create better details in the wood like bevels. Once we had shaped the wood to our liking, we then sanded the wood by starting at a low grit and increasing the grit over time.

![](/images/pen_turning/IMG_0432-resized.png)

Unfortunately, the wood that I chose was weaker than I thought and it broke while I was trying to turn it. This meant I had to get a new brass piece and a stronger piece of wood and repeat the process again.

Once this was done though, the turning went smoothly.

After we made our wood smooth, we applied a thin layer of polish to it while using the turning of the wood to apply the polish. This made the wood look very shiny and finished

![](/images/pen_turning/IMG_0066.jpg)

![](/images/pen_turning/IMG_0068.jpg)

Now all we have to do is assemble the pen, we did this by using a machine which pressed the pieces into each other tightly which allowed them to fit into one another.

![](/images/pen_turning/IMG_0436-resized.png)

This is my assembled pen.

![](/images/pen_turning/IMG_0069.jpg)

## Soldering

We were given a solderig kit and tasked to solder the pieces onto the given pcb board.

I decided to start with the chip, making sure that the dot on the pcb lined up with the dot on the chip. Since I was using thicker solder than normal this part was tricky but I was eventually able to get it done. Then I decided to solder the resistors and capacitors. Unfortunately, I had used the wrong resistors in the wrong spots so I had to get a solder sucker and take the resistors out and replace them. After they were soldered, I cut the ends using wire cutters. After this I soldered the usb attachment.

![](/images/owl_light/IMG_0048.png)

Then I soldered on each led light on the opposit side of everything else then cut the ends.

![](/images/owl_light/IMG_0050.png)

![](/images/owl_light/IMG_0054.png)

Once this was done, I plugged it in and check to see if it would work

![](/images/owl_light/IMG_0051.png)

<video width="320" height="240" controls>
  <source src="../../images/owl_light/IMG_0052.mp4" type="video/mp4">
</video>

## PCB Creation Using MakeraCAM

### MakeraCAM: Preparing Design Workflow

1. Open new 3D project
2. Set material to PCB: Edit→Material→PCB
3. Set dimensions
  <br />
  a. X = 127mm
  <br />
  b. Y  = 101mm
  <br />
  c. Z = 1.7mm
4. Download files from Fab drive: (blue folder named Dubick)
  a. Resistance1-F_Cu.gbr
  <br />
  b. Resistance1-PTH.drl
  <br />
  c. Resistance1-Edge_Cuts.gbr
5. Import each of these files in MakeraCAM:
  a. File→Import PCB→Downloads→Resistance1-Edge_Cuts.gbr→Open
  <br />
  b. File→Import PCB→Downloads→Resistance1-PTH.drl→Open
  <br />
  c. File→Import PCB→Downloads→Resistance1-F_Cu.gbr→Open
6. Anchor lower left corner:
  <br />
  a. Select whole design (highlight over everything)
  <br />
  b. Click “m” key
  <br />
  c. Select lower left corner in “Anchor” diagram at the top of new pop up (in top right corner of screen)
  <br />
  d. Under “Location” in pop up, set X to 6 and Y to 6 (offsets design from very edge of material)
  <br />
  e. Design should have moved to align with axes given
7. Path:
<br />
  a. Under “2D Layers” menu, hide (eye with red cross through):
  <br />
    i. Resistance1-F_Cu.gbr_pad
    <br />
    ii. Resistance1-PTH.drl_0.900 mm
    <br />
    iii. Resistance1-PTH.drl_1.400 mm
  <br />
  b. Select 2D Path (in tool bar)→2D Pocket
  <br />
  c. Select whole (visible) design
  <br />
  d. Set “End Depth” to .05mm
  <br />
  e. Add tool x2
  <br />
    i. 8mm Corn
    <br />
    ii. .2mm*30Engraving(Metal)
  <br />
  f. Calculate
8. Drilling holes:
<br />
  a. 2D Path→2D drilling
  <br />
  b. Under “2D Layers” menu, hide (eye with red cross through) all but file with holes to drill 
  <br />
  c. End Depth: 1.7mm
  <br />
  d. Add tool: 8mm Corn
  <br />
  e. Calculate
9. Outside cut:
<br />
  a. 2D Path→2D Contour
  <br />
  b. Under “2D Layers” menu, hide (eye with red cross through) all but file with outside cut (Resistance1-Edge_Cuts.gbr)
  <br />
  c. End Depth: 1.7mm
  <br />
  d. Strategy: Outside
  <br />
  e. Tabs: Custom
  <br />
    i. Tab Shape: Triangle
    <br />
    ii. Select “Add”
    <br />
    iii. Click 3 places on outer edge (spaced fairly evenly apart)
  <br />
  f. Add tool: 8mm Corn
  <br />
  g. Calculate
10. Path→Export→Export OR if you want to edit file on milling machine’s computer, File→Save As, save file in downloads with .mkc format (file-type)
11. Upload file to your folder in Fab google drive

#### Problems and Conclusions

I didn't have much problems while creating my PCB design. Once I got used to creating the PCB in a new software everything went pretty smoothly. It also helps that it is somewhat similar to Aspire when it comes to creating paths.

### CNC: Workflow

1. Installing material:
  a. Slightly loosen (not remove) all bolts in machine bed except the 3 that are fully within the metal jig/holder (use screwdriver on right side of machine)
  b. If copper board already on bed with design milled into bottom left corner, remove and reorient if possible or else replace
  c. Orient PCB board on CNC machine so that your design will fit in bottom left corner (as it was displayed on Makera CAM)
  d. Adjust rectangular metal holders near middle of bed (keep bolts where they are, slide and rotate rectangular piece) to be able to slide material under loosened bolts, and then do so
  e. Move/rotate both rectangular metal back so that short end of rectangle with slot aligns with material (holding it down)
  f. Screw all loosened bolts down fairly tightly (securing material, not overly tight)
2. Running file:
  a. Download gcode.nc file from Fab google drive
  b. Open Cavera Controller
  c. Open file (top left corner) → Upload File → (should be in Downloads) select your gcode file (yourfilename.nc) → “Upload & Select” 
  d. Idle (top left) → COM Port ___ (some number)
  e. Additional settings (top right dropdown) → Display Manual Controls → Home
  f. Tool status → ensure Voltage>3.6V
  g. Second most right option on bottom bar → select (check) auto vacuum + select (check) auto-levelling; select Run
  h. Machine should touch down at 25 points on material and then file should run (whole design should be automatically milled)

### Final Product and Conclusions

Using the new machine was a small learning curve (once again getting used to new software when your used to another one can be tricky at first), but once I got the hang of it I believe I can operate it safely and efficently. Interestingly, instead of milling out just the outside of the traces, the software we used mills the entire copper plate except for the traces. This makes it take a good amount of time, but problems like this can be fixed with having a bigger bit. Also, having only the traces present makes it harder to create bridges with soldering.

![](/images/pcb_beginnings/finished_pcb.jpg)