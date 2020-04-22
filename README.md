Measuring leaf area with ImageJ
================
Roman M. Link

# Introduction

This is a simple tutorial for the measurement of leaf area with
[ImageJ](https://imagej.nih.gov/ij/) based on [this great blog
post](https://rookieecologist.wordpress.com/2016/11/21/how-to-measure-leaf-area-in-imagej/)
which is meant for in-class use.

# Step-by-step tutorial

1.  Open the calibration file with ImageJ (drag and drop onto the
    program or use the Open dialog).

2.  Select the Straight line tool and follow the outer margin of the
    largest square in the calibration file.

![](figures/fig1.png)

1.  Set the scale by going to the **Analyze ➜ Set Scale** menu.

2.  In the corresponding dialog, set **Known Distance** to **4 cm**, the
    **Unit of length** to **cm** and - *very important* - mark the box
    **Global** to make sure that the scale is the same accross all
    opened documents.

![](figures/fig2.png)

1.  Open the file with the image you want to analyze in ImageJ (drag and
    drop\!). If setting the scale worked, the size of the image should
    now be specified in cm in the upper right corner of the image. If a
    popup opens asking you whether you want to keep the global
    calibration, say yes\!

![](figures/fig3.png)

1.  Make sure that the image is in an 8bit black and white format (click
    on **Image ➜ Type ➜ 8bit**) to avoid problems with thresholding.

2.  Set a black/white threshold
    
      - Open the **Threshold** dialog (**Image ➜ Threshold** or *Ctrl +
        Shift + T*),
      - Choose the options **Default** and **B\&W** and uncheck the box
        **Dark background**,
      - If necessary, move the sliders until the leafs are well
        separated from the background with as few white pixels within
        the leaves as possible,
      - press **Apply** and close the **Threshold** window.

![](figures/fig4.png)

1.  If there are holes (especially close to the leaf margins), pick the
    *Pipette* tool and click on a black area in the image.

![](figures/fig5.png)

1.  Now, choose the *Pencil tool* and close the holes manually.

![](figures/fig6.png)

1.  Open the set measurements dialog (*Analyze ➜ Set Measurements*),
    uncheck everything besides *Area*, and click *OK*.

![](figures/fig7.png)

1.  Open the *Analyze Particles* dialog (*Analyze ➜ Analyze Particles*)
    and choose the following settings:

<!-- end list -->

  - *Size*: 0-Infinity
  - *Roundness*: 0-1
  - Show: Outlines
  - Check *Display results*, *Clear results* and *Include holes*

![](figures/fig8.png)

1.  Look at the outlines to check if non-leaf particles were measured.

<!-- end list -->

  - Solutions if there are small non-leaf particles:
      - Use the pencil tool to remove small artefacts
      - Use the rectangle tool (left end of the toolbar) to choose a
        subset of the Image area (useful if there are shading artefacts
        near the borders)
      - Repeat the *Analyze Particles* step with a minimum value for
        *Size*

*initial run:* ![](figures/fig9.png)

*after setting Size to 1-Infinity cm²:* ![](figures/fig10.png)

1.  Click on the outline file and choose *File ➜ Save as ➜ Jpeg* in the
    main window to save it (append the original filename to
    `name_outlines.jpg`)

2.  Choose *File ➜ Save as* in the Results window to save the leaf area
    measurements as `name_results.xls`.

3.  Your project folder should look like this now:

![](figures/fig11.png)