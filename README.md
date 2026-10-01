# Specification Phase Exercise

A little exercise to get started with the specification phase of the software development lifecycle. In this exercise, your team specifies a set of improvements and new features for [The Slide Machine](https://theslidemachine.com) — see the [instructions](instructions.md) for detail, and the [background](background.md) for an introduction to the software product you are tasked with extending.

## Team members

Daran: dyt2010@nyu.edu | https://github.com/slvrtngd  

Tristan: ttm2041@nyu.edu | https://github.com/Trisolis

Levi: lg4493@nyu.edu | https://github.com/9021007

Robert: rf2789@nyu.edu | https://github.com/rfang1224 

Amitav: an4245@nyu.edu | https://github.com/AmitavNarayan


## Review of the Current Application
Our findings are listed below:  

1 - The app's decisions about when to create or update a slide are inconsistent; for example, sometimes continued speech produced no new slide, even after a pause. As other examples, repeating a correction after a mistake created a new slide rather than fixing the current one, and speaking for a long stretch only resulted in one slide (weakness).  

2 - The dashboard/display for the API and usage is easily accessible, very clear, and provides an ample amount of detail. The instructor can easily tell whether he/she is running close to any limits on the app (strength).  

3 - The app's support for alt text appears very limited; image descriptions usually do not contain enough information and the app defaults to the title of the slide or "Slide Image" when it's unable to produce a proper caption; instructors are also not able to modify alt text (gap).

4  - Voice commands have to start their own phrase; for example, saying “Okay, Slide Machine, next” does not work because of the “Okay” and is treated as lecture speech. Having to start with “Slide Machine” every time is difficult and confusing (weakness).  

5 - There is no way to test or adjust the microphone (run a sample sentence, for example) prior to starting the lecture (gap).  

6 - Oftentimes during a live lecture, it's unclear what the app has done or heard. In particular, after a few seconds of speech the caption text disappeared with no visible change to the deck and the user couldn't tell which speech would ultimately become slide content. The caption line did not appear for long enough to really help the user (weakness).  

7 - The app does not have video functionality. Specifically, the AI does not suggest any videos the way it does for pictures and instructors cannot add videos afterwards; correspondingly, there is no way for students to watch videos during or after the lecture (gap). 

8 - When the app captures speech correctly, the content is well-done; the app can accurately display math notation, add helpful definitions, and knows not to duplicate slides when a topic is mentioned again (strength).  

9 - There is no way for students to search through slides based on number and title (gap).

10 - Slides can only be re-ordered by dragging one at a time through the list view, which is inconvenient and time-consuming (weakness). 

11 - The whiteboard tool works well; the instructor has options to immediately draw on the board with a pen, highlighter or an eraser, and slide generation will pause automatically, or he/she can easily create a new whiteboard slide to keep drawings separate. The tool greatly enhances the instructor's ability to clarify and visualize concepts (strength). 


## Prior Art & Originality

We examined the Software Design Document, delivery roadmap, and repository issues and pull requests; none of our proposal's features are described in these sources. The current application supports drag-and-drop slide reordering when in list format and automatically assigns image alt text using one of three options: caption, slide title, or “Slide image.” Video is not currently supported as slide content.

Our proposal introduces video content (and associated features), a separate alt text field (and associated features), and much more extensive methods for slide re-organization. These changes focus on editing content rather than appearance, with the latter being outside of the scope described in the Software Design Document.



## Stakeholders

### Instructors

**Instructor A**
- Goals: Wants slides that are easy to read and uncluttered; wants proper mathematical notation/symbols for math content; wants slides clear and descriptive enough for students to follow the lecture from reading alone; wants quizzes that challenge students and promote critical thinking.
- Frustrations: The app didn't include graphs (e.g. binomial distributions) despite math-heavy content; generated quiz answer choices were too similar to each other and ambiguous; little to no LaTeX/math notation support; slides were generated in the wrong order, with title slides appearing mid-lecture.

**Instructor B**
- Goals: Wants slides that summarize lecture content using bullet points rather than paragraphs; wants all important definitions prioritized; wants images relevant to specific concepts (e.g. cinematography shots); wants the ability to link videos.
- Frustrations: Slides didn't clearly pinpoint the lecture's main topic; generated quizzes occasionally had inaccurate answers; wanted the option to use their own recorded voice for playback instead of a robotic voice; no images or videos were shown related to the lecture content.

**Instructor C**
- Goals: Wants the ability to add YouTube videos to slides; wants the ability to add alt text to images; wants a wider selection of themes, including the ability to set and actually apply a default theme.
- Frustrations: Slides did not accurately convey the lecture's content; text editing did not support click-to-place cursor; reordering slides required painful one-by-one dragging; the "API ok" indicator was confusing and distracting; found the overall site unintuitive and visually unappealing.

### Students

**Student A**
- Goals: Wants slides that include all relevant lecture information without omissions; wants the ability to download personal copies of slides to edit/comment on for studying; wants quiz questions that promote critical thinking rather than easily-searchable facts; wants all images/graphs referenced in the lecture included on slides.
- Frustrations: No easy way to download slides for personal annotation; quiz questions focused on obscure details rather than the most relevant topics; slide content wasn't specific enough for someone unfamiliar with the topic; images/graphs referenced during the lecture were missing from slides.

**Student B**
- Goals: Wants slide content specific and detailed enough to understand topics fully; wants sufficient context provided alongside content; wants quiz questions that help prepare for actual exams; wants the ability to reformat slides for better readability.
- Frustrations: Some slide text had poor grammar or unclear wording; quiz questions were too specific and didn't encourage critical thinking; slides didn't make the lecture's main topic explicit; missing images made some concepts hard to understand.

**Student C**
- Goals: Wants a wider selection of visual themes and slide transitions to stay engaged; wants image descriptions provided; wants the ability to easily identify image sources; wants an intro/conclusion slide generated automatically.
- Frustrations: Improperly-fitted images showed distracting gray borders; didn't notice the small "i" icon indicating image source; found the current visual style "painfully boring, bleak," and wanted a more polished look; would find embedded YouTube videos useful.



## Product Vision Statement

Our contribution is to improve the post-lecture capabilities of the Slide Machine; we add new features for slide organization, video content, and alternative text, so that instructors can make the final deck complete and accessible, and students can properly navigate and understand it. 


## User Requirements

### User Stories - Instructors
1. As an instructor, after my lecture has finished, I want the app to suggest videos related to what I've said, so that I don't have to manually search for relevant videos myself.
2. As an instructor, I want to add, replace, or remove the video in a slide's video box, so that I can show the video that best fits my slide/lecture.
3. As an instructor, I want to search through the slides by title or by number, so that I don't have to manually search through all the slides to find the one I want.
4. As an instructor, I want the current slide to be highlighted in the slide list, so that I can see where I am in the lecture while reorganizing slides.
5. As an instructor, I want to select multiple slides and move them simultaneously, so that I can quickly reorganize a long lecture.
6. As an instructor, I want to move a slide to a specific position by typing its number, so that I don't have to manually move it across a long lecture.
7. As an instructor, after I'm finished lecturing, I want the app to suggest alt text, so that creating alt text for images doesn't take a long time.
8. As an instructor, I want to edit the alt text for any image, so that I can modify the results of AI-generated alt text as required for specific situations.
9. As an instructor, I want to be given new alt text that I can modify whenever an image is replaced, so that the alt text doesn't describe the wrong image.
10. As an instructor, I want to mark an image as decorative (not needing alt text), so that students can skip pictures that aren't useful to them.



### User Stories - Students
1. As a student, I want to play a video right on the slide, so that I can follow along with the lecture and its context.
2. As a student, I want to turn on captions for a video, so that I'm able to better follow the video and understand its content.
3. As a student, I want a downloaded PDF of the lecture to include each video's title and link, so that I can still watch the videos from my downloaded copy.
4. As a student, I want a video to pause when I move to the next slide, so that I don't hear a video interrupting the next slide.
5. As a student, I want the current slide to be highlighted in the slide list, so that I don't lose my place while reviewing the lecture.
6. As a student, I want to move to a slide by typing its number, so that I can quickly access specific slides during lecture or while reviewing material.
7. As a student, I want to see a list of every slide's title and jump to any one, so that I can quickly access slides related to a specific topic.
8. As a student, I want image alt text to be translated when it's in another language, so that I'm able to understand the images (via the alt text) properly.
9. As a student, I want to know when an image's alt text was AI-generated, so that I know how much to trust it and can ask my instructor if it seems wrong.
10. As a student, I want to click an image to see its alt text, so that I can clarify the meaning of the image.
11. As a student, I want alt text to be included in any copy of the slides (e.g., pdf) I download, so that I can still access slide content completely and in all circumstances.
12. As a student, I want alt text to properly describe an image's content, so that I can fully understand the presentation with all available context. 

## Activity Diagrams




#### Diagram 1 

**User story:** As an instructor, I want to move a slide to a specific position by typing its number, so that I don't have to manually move it across a long lecture.

![Activity diagram](media/diagrams/InstructorMoveSlide.png)


#### Diagram 2 

**User story:** As an instructor, I want to edit the alt text for any image, so that I can modify the results of AI-generated alt text as required for specific situations.


![Activity diagram](media/diagrams/InstructorAltText.png)

#### Diagram 3

**User story:** As a student, I want to play a video right on the slide, so that I can follow along with the lecture and its context.

![Activity diagram](media/diagrams/StudentPlayVideo.png)


#### Diagram 4

**User story:** As a student, I want to see a list of every slide's title and jump to any one, so that I can quickly access slides related to a specific topic.

![Activity diagram](media/diagrams/StudentMoveSlide.png)



## Wireframes

### Instructors

**1 - Home**
![1-Home](media/Wireframes/01-Home.png)

**2 - Live Lecture**
![2-Live-Lecture](media/Wireframes/02-Live-Lecture.png)

**3 - Post-Lecture Review**
![3-Post-Lecture-Review](media/Wireframes/03-Post-Lecture-Review.png)

**4 - Lecture Page**
![4-Lecture-Page](media/Wireframes/04-Lecture-Page.png)

**5 - Navigate Search**
![5-Navigate-Search](media/Wireframes/05-Navigate-Search.png)

**6 - Lecture Page (Slide 5)**
![6-Lecture-Page-Slide-5](media/Wireframes/06-Lecture-Page-Slide-5.png)

**7 - Slide Menu**
![7-Slide-Menu](media/Wireframes/07-Slide-Menu.png)

**8 - Move Slide Box**
![8-Move-Slide-Box](media/Wireframes/08-Move-Slide-Dialog.png)

**9 - Slide Moved**
![9-Slide-Moved](media/Wireframes/09-Slide-Moved.png)

**10 - Select Multiple**
![10-Select-Multiple](media/Wireframes/10-Select-Multiple.png)

**11 - Move Selected Box**
![11-Move-Selected-Box](media/Wireframes/11-Move-Selected-Dialog.png)

**12 - Slides Moved, Empty Video Box**
![12-Slides-Moved-Empty-Video-Box](media/Wireframes/12-Slides-Moved-Empty-Video-Box.png)

**13 - Add Video Box**
![13-Add-Video-Box](media/Wireframes/13-Add-Video-Dialog.png)

**14 - Video Box Menu**
![14-Video-Box-Menu](media/Wireframes/14-Video-Box-Menu.png)

**15 - Alt Text Pop-up**
![15-Alt-Text-Pop-up](media/Wireframes/15-Alt-Text-Popup.png)

**16 - Replace Image**
![16-Replace-Image](media/Wireframes/16-Replace-Image.png)

**17 - New Image, Suggested Alt Text**
![17-New-Image-Suggested-Alt-Text](media/Wireframes/17-New-Image-Suggested-Alt-Text.png)

### Students

**1 - Lecture Viewer**
![1-Lecture-Viewer](media/Wireframes/S01-Lecture-Viewer.png)

**2 - Navigate Search**
![2-Navigate-Search](media/Wireframes/S02-Navigate-Search.png)

**3 - Video Playing, Captions On**
![3-Video-Playing-Captions-On](media/Wireframes/S03-Video-Playing-Captions-On.png)

**4 - Next Slide, Video Paused**
![4-Next-Slide-Video-Paused](media/Wireframes/S04-Next-Slide-Video-Paused.png)

**5 - Alt Text (Read-Only)**
![5-Alt-Text-Read-Only](media/Wireframes/S05-Alt-Text-Read-Only.png)

**6 - Translated Alt Text**
![6-Translated-Alt-Text](media/Wireframes/S06-Translated-Alt-Text.png)

**7 - Download Box**
![7-Download-Box](media/Wireframes/S07-Download-Dialog.png)

**8 - Downloaded PDF**
![8-Downloaded-PDF](media/Wireframes/S08-Downloaded-PDF.png)

## Clickable Prototype

Our clickable prototype is linked [here](https://www.figma.com/proto/on8UZbwKyV92jfbVAYYgau/FinalPrototype?t=gmwXNFRIOvkc4vVn-1&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&node-id=1-2&starting-point-node-id=1%3A2&show-proto-sidebar=1).

## Stakeholder Demo

Our slide machine deck is linked [here](https://theslidemachine.com/d/untitled-7f9e4853).

## Exit Ticket

Our exit ticket quiz is linked [here](https://docs.google.com/forms/d/e/1FAIpQLSfoRlvjHWWZQmPQDgJ3bvtOLkrk5u46saPPfVZgdBA72VHuiw/viewform?usp=header).  
We had to modify a question which asked for the slide number of the vision statement, and replaced it with a more logical question about stakeholder interview coverage. We also removed a question that asked responders to distinguish between stakeholder interviews and other methods of gathering information, as it would have been obvious to any student who worked on this project, and replaced it with a question about slide search, a specific feature our demo introduces.
