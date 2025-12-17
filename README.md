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
  - a. X = 127mm
  - b. Y  = 101mm
  - c. Z = 1.7mm
4. Download files from Fab drive: (blue folder named Dubick)
  - a. Resistance1-F_Cu.gbr
  - b. Resistance1-PTH.drl
  - c. Resistance1-Edge_Cuts.gbr
5. Import each of these files in MakeraCAM:
  - a. File→Import PCB→Downloads→Resistance1-Edge_Cuts.gbr→Open
  - b. File→Import PCB→Downloads→Resistance1-PTH.drl→Open
  - c. File→Import PCB→Downloads→Resistance1-F_Cu.gbr→Open
6. Anchor lower left corner:
  - a. Select whole design (highlight over everything)
  - b. Click “m” key
  - c. Select lower left corner in “Anchor” diagram at the top of new pop up (in top right corner of screen)
  - d. Under “Location” in pop up, set X to 6 and Y to 6 (offsets design from very edge of material)
  - e. Design should have moved to align with axes given

Once your file looks like this you're ready to move on.

![](/images/pcb_beginnings/pcb_beginnings-w1.png)

7. Path:
  - a. Under “2D Layers” menu, hide (eye with red cross through):
    - i. Resistance1-F_Cu.gbr_pad
    - ii. Resistance1-PTH.drl_0.900 mm
    - iii. Resistance1-PTH.drl_1.400 mm
  - b. Select 2D Path (in tool bar)→2D Pocket
  - c. Select whole (visible) design
  - d. Set “End Depth” to .05mm
  - e. Add tool x2
    - i. 8mm Corn
    - ii. .2mm*30Engraving(Metal)
  - f. Calculate
8. Drilling holes:
  - a. 2D Path→2D drilling
  - b. Under “2D Layers” menu, hide (eye with red cross through) all but file with holes to drill 
  - c. End Depth: 1.7mm
  - d. Add tool: 8mm Corn
  - e. Calculate
9. Outside cut:
  - a. 2D Path→2D Contour
  - b. Under “2D Layers” menu, hide (eye with red cross through) all but file with outside cut (Resistance1-Edge_Cuts.gbr)
  - c. End Depth: 1.7mm
  - d. Strategy: Outside
  - e. Tabs: Custom
    i. Tab Shape: Triangle
    ii. Select “Add”
    iii. Click 3 places on outer edge (spaced fairly evenly apart)
  - f. Add tool: 8mm Corn
  - g. Calculate

Your file should look like this

![](/images/pcb_beginnings/pcb_beginnings-w2.png)

10. Path→Export→Export OR if you want to edit file on milling machine’s computer, File→Save As, save file in downloads with .mkc format (file-type)
11. Upload file to your folder in Fab google drive

#### Problems and Conclusions

I didn't have much problems while creating my PCB design. Once I got used to creating the PCB in a new software everything went pretty smoothly. It also helps that it is somewhat similar to Aspire when it comes to creating paths.

### CNC: Workflow

1. Installing material:
  - a. Slightly loosen (not remove) all bolts in machine bed except the 3 that are fully within the metal jig/holder (use screwdriver on right side of machine)
  - b. If copper board already on bed with design milled into bottom left corner, remove and reorient if possible or else replace
  - c. Orient PCB board on CNC machine so that your design will fit in bottom left corner (as it was displayed on Makera CAM)
  - d. Adjust rectangular metal holders near middle of bed (keep bolts where they are, slide and rotate rectangular piece) to be able to slide material under loosened bolts, and then do so
  - e. Move/rotate both rectangular metal back so that short end of rectangle with slot aligns with material (holding it down)
  - f. Screw all loosened bolts down fairly tightly (securing material, not overly tight)
2. Running file:
  - a. Download gcode.nc file from Fab google drive
  - b. Open Cavera Controller
  - c. Open file (top left corner) → Upload File → (should be in Downloads) select your gcode file (yourfilename.nc) → “Upload & Select” 
  - d. Idle (top left) → COM Port ___ (some number)
  - e. Additional settings (top right dropdown) → Display Manual Controls → Home
  - f. Tool status → ensure Voltage>3.6V
  - g. Second most right option on bottom bar → select (check) auto vacuum + select (check) auto-levelling; select Run
  - h. Machine should touch down at 25 points on material and then file should run (whole design should be automatically milled)

### Final Product and Conclusions

Using the new machine was a small learning curve (once again getting used to new software when your used to another one can be tricky at first), but once I got the hang of it I believe I can operate it safely and efficently. Interestingly, instead of milling out just the outside of the traces, the software we used mills the entire copper plate except for the traces. This makes it take a good amount of time, but problems like this can be fixed with having a bigger bit. Also, having only the traces present makes it harder to create bridges with soldering.

I'm very interested in this machine because there are many other materials that I can cut using this. I was thinking that I could potentially use this machine to cut out aluminum in order to create better crank shafts in my personal project. Utilizing aluminum can help the deformation issues that I was encountering in the project.

I'm also very excited to try and design my own pcb boards. Being able to have the machine run itself is great seeing that I would have to watch the milling machine almost every time before. 

![](/images/pcb_beginnings/finished_pcb.jpg)

You can download my files for making this PCB [here](/assets/EP-pcb_beginnings.zip)

## Topography Map

We were tasked of making a topography map by cncing wood of a mountain of our choice. First, we visited [Terrain2STL](https://jthatch.com/Terrain2STL/) which would create an .stl of a specified part of the earth that we wanted so we can utilize it in order to create a .cnc file in Aspire to cut on the Cavera. I decieded to choose a part of the Andes mountains in Peru. I edited to settings to increase the Vertical Scaling.

![](/images/topography_map/ep_terrain2stl.png)

Then I took this file into Aspire then followed a given workflow to turn the file into a .cnc file that I could use to mill. We made roughing pass with a larger bit to remove as much material as possible quickly and then a finishing pass with a ball-point, smalelr bit to get the details of the mountain. 

<iframe src="https://drive.google.com/file/d/1A2KOTGyH5LuEHXZDqpiYKwSuG7LrYfh6/preview" width="640" height="480"></iframe>

I had little problems going through this guide and creating my file.

![2D View](/images/topography_map/ep-aspire_2dview.png)

![3D View](/images/topography_map/ep-aspire_3dview.png)

Once I exported the drill files, I went to the Cavera CNC machine and locked my wood in place in the corner of the machine, making sure it was flush to the edge. 


Then I Uploaded and Selected my file then homed the machine. 

![](/images/topography_map/SS-fileupload.png)

I then repositioned the cut to make sure to cut from the corner where my wood was positioned and turned on auto-leveling.

![](/images/topography_map/Auto_level.png)

![](/images/topography_map/ss-gcodeview.png)

When I sent the file I made sure that the laser which outlines the cut stayed inside the wood block. Then I sent the file and let it cut.

Here is my finsihed topography map

![](/images/topography_map/ep-finished_topography.jpg)

### Download

You can downlaod my aspire and cnc files [here](/assets/EvanPark_MountainRange_Andes.zip)