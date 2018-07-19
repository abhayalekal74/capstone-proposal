Obtaining input images:

1. Make 6 directories namely eng-train, eng-test, hin-train, hin-test, math-train, math-test
2. The repo consists of 6 files starting with "ud_" which contain the URLs for images to be downloaded.
3. The names of those 6 files are self explainatory. For eg: if the name is "ud_english_train" these images should be downloaded to the eng-train folder.
4. To download: 
    -   copy the respective "ud_" file to the appropriate folder.
    -   run this command 
            cat <ud_file_name> | xargs -I{} -P 20 wget {}
    - This command will download the images from the "ud_" file into that folder.
5. Some images are pngs and some are jpegs. We don't want the model to learn on this difference, so we convert every file to a "jpeg" image.
    To do so, run this command in all of the six folders.
        ls | xargs -I{} mv {} {}.jpeg
    All the images will have .jpeg at the end. 
    
That is it, the dataset is ready.
