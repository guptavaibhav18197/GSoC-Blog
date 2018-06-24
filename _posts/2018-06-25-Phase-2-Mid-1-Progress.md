---
layout: post
title: "Phase 2 Mid 1 Progress"
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

## Designed Add Label and Annotation Level Page
Designing of this page was not finalized during pre-project phase. I have used _ajax calls_ so that user need not wait for the page refreshes. So almost everything(from adding labels to deleting / editing labels and annotation) done asynchronously and hence is quite responsive.

I designed it initially as a 2 column view for lables but was then directed to rather make it single column view. Hence, the final outlook of the page is as below

![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/addLabelsPage.png)

## PlUpload for uploading files
Use PlUpload to upload files (multiple files together also possible) manually. It has provision for
*   adding,
*   deleting and
*   editing file caption.

Here also I have used _ajax calls_ for almost everything.
Hence, the final outlook of the page is as below
![image](https://guptavaibhav18197.github.io/GSoC-Blog/assets/images/uploadFiles.png)

## Work left to do in phase 2
Now I will be working on _view_experiment package_ and _results page_.


[repository-link]: https://github.com/guptavaibhav18197/rapidannotator
