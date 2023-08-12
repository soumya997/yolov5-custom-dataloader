# yolov5-custom-dataloader

This is a solution for the assignment. There are 3 versions of the solution. V3 is the final solution. I gradually built up from V1 to V3. you can checkout all versions, or only V3.



### Files to Check:
- **V1:** The code for this is provided in the `CustomLoadImagesAndLabels` class at `yolov5/utils/custom_dataloaders.py` file and demonstrated at `yolov5/custom_dataloader_w_labels.ipynb` file.

- **V2:** The code for this is provided in the `CustomDataset` class at `yolov5/utils/only_img_cus_dataloaders.py` file, and demonstrated at `yolov5/simple_custom_dataloader_wo_labels.ipynb`.

- **V3:** The code for this is provided in the `CustomDataset` class at `yolov5/utils/only_img_custom_aug_dataloader.py` file and its demonstrated at `yolov5/custom_dataloader_aug_wo_labels.ipynb`.

### About the Repository:
- This is the repository for the yolov5 dataloader modification.
- The modifications are done by the instructions mentioned in the assignment pdf.
- The development is done in 3 steps,
    + **"Version 1: Modification of Existing Dataloader BUT by preprocessed .txt annotation files".** I preprocessed the data and created annotation files, for model training. The code for this is provided in the `CustomLoadImagesAndLabels` class at `yolov5/utils/custom_dataloaders.py` file. And the code use and training is done at `yolov5/custom_dataloader_w_labels.ipynb` file. I used simple **template matching** for generating the annotations. It has all the features that the original dataloader has, its just that I modified the data loader according to the instructions (cropping, random pasting).

    + **"Version 2: Very Simple Scratch Dataloader that doesnt Uses Annotation .txt Files":** I wrote a very simple custom dataloader, that only loads the images, does template matching and generates bbox labels and uses that for training. Everything is done on the fly. The code for this is provided in the `CustomDataset` class at `yolov5/utils/only_img_cus_dataloaders.py` file, and demonstrated at `yolov5/simple_custom_dataloader_wo_labels.ipynb`.

    + **"Version 3: Scratch Dataloader with Augmentaion Enebled that doesnt Uses Annotation .txt Files":** This is modification on version 2. I only enabled the augmentation features, everying is same except that. The code for this is provided in the `CustomDataset` class at `yolov5/utils/only_img_custom_aug_dataloader.py` file and its demonstrated at `yolov5/custom_dataloader_aug_wo_labels.ipynb`.
 
- A detailed code comments are provided in the `yolov5/utils/only_img_cus_dataloaders.py` file, other files are similar to this file's comments.
- The solutions can be improved, wight now we are using template matching for extracting the fingerprint. But, we can also modify this and use some other techniques that can improve the bbox extraction.
- There is also overlapping issue, two fingerprint sometimes overlaps each other, we can also avoid that internally.
- There many other things that need to be improved, but I think the dataloaders are created correctly(as much as i could). its also tested by running the training code. I could many other changes but because of time constrain, this is all i could do. Please let me know, if there is any issue understanding the code, or how can i improve that.

### Debugging:
- mention the file paths properly.
- check if you changed the import for specific version of dataloader in the `yolov5/train.py` file.