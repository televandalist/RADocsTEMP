In "Window Capture" mode, OBS Studio will not capture the popups. The popups are rendered using a "Layered Window", and OBS Studio removed support for capturing layered windows

If you want to include the popups in your stream, you have two options: change to "Display Capture" mode, or add a second "Window Capture" for the "TransparentOverlayWindow". This page will attempt to walk you through doing the second.

Add a second "Window Capture" source to the Scene. In the popup dialog, select the "TransparentOverlayWindow".

![Add second "Window Capture"](/images/tutorials/obs-studio/obs1.png)

You'll probably notice the window is pink.

![Pink overlay](/images/tutorials/obs-studio/obs2.png)

Add a filter to the second "Window Capture"

![Add filter](/images/tutorials/obs-studio/obs3.png)

Add a "Color Key" filter, set the Key Color Type to "Custom Color", then use the Select Color dialog to enter `#FF01FE` as the color. Decrease the similarity to 1 and the opacity to 90.

![Color Key properties](/images/tutorials/obs-studio/obs4.png)

Finally, if you still have a bit of a pink border showing up, enable a Scale Filter. They all seem to eliminate the remnant, so choose whichever you like best.

![Scale Filter](/images/tutorials/obs-studio/obs5.png)


