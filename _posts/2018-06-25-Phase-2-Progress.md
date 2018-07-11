---
layout: post
title: "Phase 2 Progress"
---

By the end of Phase 1, I accomplished all the intended tasks.

# Phase 1 at a glance

*   Completed **Backend Implementation**.
*   Wrote some _Generic and Reusable code snippets_.
*   Completed **frontpage** package.
*   Completed **home** package.
*   Started implementing **add_experiment** package.

This phase is headed towards completing **add_experiment** and **view_experiment** packages. It also involves implementing _results page_ where experiment owners can view a summary of all the annotation progress.

# Progress made so far
Again, I am strictly following the timeline proposed in the project proposal and have been able to convey all the deliverables as per the timeline as of now. Apropos of deliverables, code has been pushed to the github repository [Rapid Annotator][repository-link].

### PlUpload for uploading files
Use PlUpload to upload files (multiple files together also possible) manually. It has provision for
*   adding,
*   deleting and
*   editing file caption.

Here also I have used _ajax calls_ for almost everything.
Hence, the final outlook of the page is as below
![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/uploadFiles.png)

Also as decided upon discussions with mentors : we have clubbed **view_experiment** and
**add_experiment** packages under the name **add_experiment**.

### Rationale for clubbing add_experiment and view_experiment
* These 2 packages shared much of the functionality like adding labels / add-remove annotators-owners / adding files and so on.
* So in view of _DRY_(don't repeat yourself) principle I think it would be best if these 2 packages could be clubbed together.

Now, we have a separate module instead of _view_experiment_ package - where user can modify the settings of the experiment like - changing displayTime of experiment, assign different files to different annotators, view results, delete experiment and so on. This module is contained in add_experiment package.

## results package

* Table showing the annotations progress.
* Discard Annotations button to discard all the annotations till now.

![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/results.png)


We have decided to finish the project as soon as possible, giving ample time for the users to use it and get back with suggestions possible need of improvement if required.

I have henceforth start with the final phase work as well.

## annotate_experiment package

* Display labels corresponding to the current annotation level and their key bindings along with the corresponding instructions.
* Turn On / Off looping button for audio / video clips

Most of this package except undo feature has been implemented.

![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/annotate_experiment.png)


## Designed Add Label and Annotation Level Page
Designing of this page was not finalized during pre-project phase. I have used _ajax calls_ so that user need not wait for the page refreshes. So almost everything(from adding labels to deleting / editing labels and annotation) done asynchronously and hence is quite responsive.

I designed it initially as a 2 column view for lables but was then directed to rather make it single column view. Hence, the final outlook of the page is as below

![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/addLabelsPage.png)


## Work left to do in final phase

* **admin package**
* few stuff that needs to be tied up to finish with the development phase of Rapid Annotator.

[repository-link]: https://github.com/guptavaibhav18197/rapidannotator
