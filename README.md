# GrabCut

GrabCut is an interactive segmentation method. Which allows the user to determine the
Region of interest (to be extracted as the foreground). GrabCut perform segmentation of
objects as foreground and background by reducing an energy function. The minimisation
of the energy function is done by Mincut - Maxflow algorithm. Grabcut algorithm can be
considered to be as a two class classification problem.
GrabCut performs segmentation on the intensity values. By specifying the Region of
Interest (ROI) the user provides the in general colour distribution of the foreground region
and the image excluding the ROI is used to determine the colour distribution of
background region.
To implement Mincut - Maxflow algorithm, we need to determine the dataterm and
interaction term between the neighboring nodes. The values of the dateterm are
determined from the Gaussian Mixture Models (GMM) which are used to learn the colour
distribution. There are two GMMs used, one for the foreground and other for the
background. Using GMM we determine each node being foreground object or background
object. The dataterm is logarithmic value of the probability predicted by the GMMs for the
particular pixel node.
Interaction term is calculated between neighboring pixel nodes. The interaction term is
determined by the Manhobalis distance between the colour values of the pixels. If the
colour pixel values of neighboring nodes are different than the interactive term value will
be large.
