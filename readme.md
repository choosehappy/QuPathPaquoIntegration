Here you find the code that is used in the blog post "Using Paquo to directly interact with QuPath project files for usage in digital pathology machine learning" at [Andrew Janowczyk's Website](http://www.andrewjanowczyk.com/using-paquo-to-directly-interact-with-qupath-project-files-for-usage-in-digital-pathology-machine-learning/).

This is an updated version of the previously described workflow on how to load and classify annotations/detections created in QuPath for usage in downstream machine learning workflows. [The original post](http://www.andrewjanowczyk.com/exporting-and-re-importing-annotations-from-qupath-for-usage-in-machine-learning/) described how to use the Groovy programming language used by QuPath to export annotations/detections as GeoJSON from within QuPath, made use of a Python script to classify them, and lastly used another Groovy script to reimport them. 

Here we present an updated approach which makes use of [paquo](https://paquo.readthedocs.io/), a Python library for interacting with QuPath, to directly read, create, and modify annotations and/or detections (among many other things outside the scope of this post). This approach yields a new QuPath project based on an input QuPath project which has been processed by a Python-based algorithm for Deep Learning (DL) predictions to assign object labels.

In addition, we make use of [papermill](https://papermill.readthedocs.io/), a library for parameterizing and executing Jupyter Notebooks. While potentially a bit contrived in this situation, this approach is quite handy, and can easily be generalized to many other use cases so is worth familiarizing yourself with.

Last but not least, we speed up the reading of image tiles by facilitating the use of [tiffslide](https://github.com/bayer-science-for-a-better-life/tiffslide), a tiffiles-based drop-in replacement for openslide-python. 


Code and blog written by Sabina Köfler (sabina.koefler@jku.at) with huge support from Andrew Janowczyk (https://github.com/choosehappy/) and Andreas Poehlmann (https://github.com/ap--).

