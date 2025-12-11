# 🚩 Syllabus

## Course Goals
Cadets shall develop the skills to design, implement, test, and debug microcontroller-based systems by developing operational assembly and C language programs that incorporate the built-in microcontroller functions, and by successfully interfacing the microcontroller to the external world.

## Course Objectives
Cadets shall be able to:
- Utilize the built-in functional units of a specified microcontroller.
- Write, assemble, link, and run microcontroller code in assembly language.
- Write, compile, assemble, link, and run microcontroller code in the C programming language.
- Interpret and explain orally and in writing the functions of a given assembly language or C program as well as laboratory work.
- Evaluate, analyze, debug, and modify a given program to improve its execution of a specified task.
- Demonstrate a working knowledge of the on-board hardware components of a microcontroller and implement an interface between a specified microcontroller and other hardware.
- Demonstrate the ability to solve well and ill-defined problems.

## Course Prerequisites
CS 110 and ECE 281

## Course Schedule
The course schedule is [here](schedule.md)

## Grade Distribution and Policy

The **Grade distribution** for this course is shown below.

|     Prog                  |             |     Final              |             |
|---------------------------|-------------|------------------------|-------------|
|     GRs                   |     22.9%   |     GRs                |     18%     |
|     Labs                  |     35.9%   |     Labs               |     32%     |
|   Homework                |     41.2%   |     Homework           |     25%     |
|                           |             |     Final Project      |     25%     |
|                           |             |                        |             |
|     Total                 |     100%    |     Total              |     100%    |


```{raw} html
<style>
  .chart-container {
    display: flex;
    justify-content: center;
    gap: 40px;
    padding: 1rem;
    flex-wrap: wrap;
  }
  canvas {
    max-width: 300px;
    max-height: 300px;
  }
</style>

<div class="chart-container">
  <div>
    <canvas id="progChart"></canvas>
  </div>
  <div>
    <canvas id="finalChart"></canvas>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-datalabels@2"></script>
<script>
  Chart.register(ChartDataLabels);

  const commonOptions = {
    plugins: {
      datalabels: {
        color: '#ffffff',
        font: {
          weight: 'bold'
        },
        formatter: (value, ctx) => {
          let label = ctx.chart.data.labels[ctx.dataIndex];
          return `${label}\n${value}%`;
        }
      },
      tooltip: {
        enabled: false
      },
      legend: {
        display: false
      }
    }
  };

  new Chart(document.getElementById('progChart'), {
    type: 'pie',
    data: {
      labels: ['GR', 'Labs', 'Homework'],
      datasets: [{
        data: [22.9, 35.9, 41.2],
        backgroundColor: ['#1f77b4', '#ff7f0e', '#2ca02c']
      }]
    },
    options: {
      ...commonOptions,
      plugins: {
        ...commonOptions.plugins,
        title: {
          display: true,
          text: 'Prog Grade Breakdown',
          color: '#ffffff'
        }
      }
    }
  });

  new Chart(document.getElementById('finalChart'), {
    type: 'pie',
    data: {
      labels: ['GRs', 'Labs', 'Homework', 'Final Project'],
      datasets: [{
        data: [18, 32, 25, 25],
        backgroundColor: ['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728']
      }]
    },
    options: {
      ...commonOptions,
      plugins: {
        ...commonOptions.plugins,
        title: {
          display: true,
          text: 'Final Grade Breakdown',
          color: '#ffffff'
        }
      }
    }
  });
</script>
```


<br>

Electrical and Computer Engineering courses are contract graded using the following 100 point scale.
<br>

|     Grade       |     Grade      |     Grade       |     Grade     |   
|:---------------:|:--------------:|:---------------:|:-------------:|
| 93 <= A <= 100  | 87 <= B+ < 90  | 77 <= C+ < 80   | 60 <= D < 70  | 
| 90 <= A- < 93   | 83 <= B < 87   | 73 <= C < 77    | 0 <= F < 60   | 
|                 | 80 <= B- < 83  | 70 <= C- < 73   |               |


You must complete all minimum functionalities on labs in order to complete the course.  Even if an assignment is so late that no credit will be received, the assignment must be completed to the satisfaction of the instructor to prevent a grade of “Incomplete.”

## Primary Communication and Control (C2)
All communication and course material will be provided through a course and section Team. Additionally, videos will be uploaded to a YouTube channel for your convenience. Lastly, Bitbucket will be used for cadets to provide their source code for laboratories.

## Textbooks
**Required:**
[Embedded Systems: Introduction to Robotics](https://www.amazon.com/Embedded-Systems-Introduction-Jonathan-Valvano/dp/1074544307), Johnathan W. Valvano, First Edition, 2019. ISBN: 978-1074544300.

**GRs are open-book exams and this textbook may be used during GRs.** 

**Optional:**
Embedded Systems: Introduction to the MSP432 Microcontroller (Vol 1), Johnathan W. Valvano, First Edition, 2019. ISBN: 978-1512185676.

## Collaboration & AI Policy

Unless specifically directed otherwise, the collaboration policy for this course is:

- For all assignments in this course, unless otherwise noted on the assignment, you may collaborate with any other cadets currently enrolled in ECE 382. We expect all graded work to be in your own work. Copying another person’s work, with or without documentation, will result in NO academic credit. Furthermore, copying without attribution is dishonorable and will be dealt with as an honor code violation.
- GRs are individual efforts. No collaboration is allowed while taking these exams. All electronic devices (phones, smartwatches, computers, tablets, etc.) must be placed out of sight for the duration of the event. If any electronic device is seen during the event, the student will receive a zero for that effort. 
- Authorized resources include any material from the ECE 382 course site and online sources regarding C programming syntax only. This does not include any solutions or solution stubs for challenges similar to those asked in any assignments.
- AI usage is limited to Level 3.  Level 3 is defined as "Use of GenAI as a feedback tool on student-generated work. Cadets create their own work independently, then may use GenAI as a tool to get feedback about their draft, such as suggestions for improvement, clarification, alignment with the assignment instructions, or editing tips. Cadets are expected to make their own revisions based on this feedback; the submitted work should not include GenAI-generated text. This use of GenAI should be clearly communicated in their documentation statements."  This means you must write your own code but can ask an AI model for clarification, conceptual questions, and debugging help.  You should not have the AI model write the solution for you and should put language in your prompt that asks the AI to not write the code for you.  You must provide your instructor with a transcript of your conversation.

## Documentation Requirements

**Documentation Requirements**: You must document all help received from any sources other than your instructor or instructor-provided course materials (including your textbook). 
- Each documentation statement must be specific enough to explicitly describe what assistance was provided, how it was used to complete the assignment, and who provided the assistance.
- If no help was received on this assignment, the documentation statement must state “None.”
- If you checked answers with anyone, you must document with whom on which problems. You must document whether you made any changes or not.  If you did make changes, you must document the problems you changed and the reasons why.
- Vague documentation statements will result in a 5% deduction on the assignment.

### Sample Documentation 
Consider the following examples when writing your own detailed documentation statements:

**Bad Example**:  Cadet McFly explained how the factorial worked.
<br>
**Good Example**: Cadet McFly explained how a recursive function worked conceptually, using diagrams and the assignment materials. He did not look at my code nor did I look at his code during this discussion.

**Bad Example**: : Cadet McFly helped fix my factorial() method.
<br>
**Good Example**: Cadet McFly helped fix my factorial() method by looking at my code** and finding that I had n > 0 instead of n >= 0 on line 85. _Note: A situation such as this may result in **less than full credit for the factorial() method, but due to the documentation statement there is no violation of the honor code._

**Bad Example**: : Cadet McFly and I worked together on the factorial() method.
<br>
**Good Example**: Cadet McFly and I worked together on the factorial() method, each contributing equally to its development. Prior to this help, neither of our factorial() methods was working. My factorial() method is now nearly identical to Cadet McFly's factorial() method. _Note: In a situation such as this, at most half-credit would be earned for the factorial() method, but due to the documentation statement there is no violation of the honor code._

**Bad Example**: : Cadet McFly showed me how the factorial() method works.
<br>
**Good Example**: Cadet McFly showed me how the factorial() method works by letting me look at his code. Prior to this help, my own factorial() method was not working.  My factorial() method is now nearly identical to Cadet McFly's factorial() method. _Note: In a situation such as this, no points would be earned for the factorial() method, but due to the documentation statement there is no violation of the honor code._

**Bad Example**: : Cadet McFly showed me how the factorial() method works.
<br>
**Good Example**: Cadet McFly showed me how the factorial() method works by looking at my code and talking me through each line as I wrote it. Prior to this help my own factorial() method was wrong.  My factorial() method is now nearly identical to Cadet McFly's factorial() method. _Note: In a situation such as this, no points would be earned for the factorial() method, but due to the documentation statement there is no violation of the honor code._

## Extra Instruction (EI)

Schedule EI with an instructor if you are having difficulty with the course material.  You must have read the assignment and attempted the homework before requesting EI.  Note:  You are responsible for material if you miss class, so get notes from someone in your section.  For example, you miss the lesson where the instructor announces a quiz for the next lesson or the instructor assigns homework due next lesson.  Even though you missed the lesson, you are still responsible for the quiz, homework, or any other assignments made.  It is in your best interest to check with your classmates after an absence.  After you’ve read the assignment, attempted the homework, and checked with your classmates, you may then schedule EI if you have difficulty with the material—not to make up a class you missed.

## CAS Policy  
For CAS notification, email your instructor prior to your absence and include the lesson number, the date, and the reason (descriptive reason—don’t just send a CAS code or SCA number) as soon as possible, preferably before the absence occurs.  It is your responsibility to check your SCA to see if instructor permission is required.  If it is, you must make the request prior to your absence.  If you miss class, you are responsible for all material (e.g. assignments, notes, announcements, handouts, etc.) covered in class.  Please check with another cadet in your section to find out what you missed.  

When a cadet is absent on the day that an assignment is due, or on the date of a quiz or GR, the cadet is responsible for meeting the following standards: 
- Scheduled Absence: If a cadet will miss any graded event due to a scheduled absence such as an SCA, sport team trip, or scheduled lasik surgery, the cadet is expected to complete all work BEFORE the absence.  
- Unscheduled Absence: If a cadet misses a graded event for an unscheduled reason such as AOC approved bedrest or a family emergency, the cadet must complete all work on the first full class day that they return to duty in order to avoid a late penalty.  For example, if a cadet is on AOC bedrest for a GR on M17 and can return to duty on T17 or M18, the cadet is expected to make up the work by M18.
- Unique Circumstances: For circumstances that do not fall under either of these broad categories (e.g. concussion protocol), the cadet is expected to communicate early and often with the instructor.  The instructor and course director will work with the cadet on a course of action.

## Late Work Policy
All work is due as shown on Gradescope. If problems arise with graded assignments, see your instructor in advance. 
- The cutoff for on-time submission is 0700 on the due date. 
- Late days are counted in 24-hour periods. Submitting between 07:00:01 on the due date and 07:00:00 the next day is one day late, and so on.
- You are given 5 grace days (self-granted extensions) which you can use to give yourself extra time without penalty. No more than 2 grace days can used for each assignment.
- Instructor-granted extensions are only considered after all grace days are used and only given in exceptional situations. Computer problems such as hard-drive reimaging are not considered as exceptional situations and you must use grace days.
- Late work handed in when you have run out of grace is discounted up to 20% for the first day late and up to 15% per day late thereafter.
- Every assignment has a hard deadline; 4 calendar days past the original due date. 
- Late submissions (penalty or not) are not accepted after the hard deadline or after the solution to the assignment is published. No late submissions (penalty or not) will be accepted for the assignments right before GRs.


## Assignments
Assignments and due dates are included in Gradescope.

## Exams and Quizzes  
GRs are open-book exams. Cadets may bring in the following items 
- Textbook: Embedded Systems: Introduction to Robotics
- One-page handwritten letter-size note
- Printed copy of GR Reference Guide (PDF version is located in Teams under Files > Admin) 

Testable material includes any concepts from the labs, lectures, exercises, homework, and assigned readings.  Not all testable concepts will necessarily be covered in class (e.g., readings).

For missed GRs, the following policies are outlined in USAFA FOI 537-3:
- Scheduled Absence - If you know that you will be unable to take the GR during the scheduled GR period, you are required to inform your instructor as soon as possible before the GR and to schedule a make-up exam.
- Unscheduled Absence - If you miss the GR for reasons beyond your control (e.g. hospitalization, emergency leave, delayed field trip return, etc.), you must contact DFEC (x3190) within two working days to schedule a makeup.  Exceptions can only be granted by the Department Head.

## Laboratories
Labs are held in 2E48, but may include a prelab assignment that must be done before coming to class.  The labs tend to be very hardware/software intensive and will probably require debugging to isolate and fix problems.  In-class time is your primary chance to get active help for these problems so the more you prepare outside of class, the more successful you’ll be.  The 53 minutes go by extremely fast - don’t waste them!

## Final Project
The final project will be a culmination of the learned material and will include a robot maze and competition. The final project will include a formal laboratory write-up, demos, and seven-minute design presentation. The final project is worth 25% of your final grade.

## Miscellaneous
This course is designed to help in your development as an engineer.  Feel free to provide feedback on the lessons and labs at any time.  If you have ideas to improve or enhance the course, please let me know.  The class builds on concepts from the prerequisites, so it is important for you to seek help as soon as you need it.  Procrastination is truly the enemy in a design course.  A little foresight and planning and a lot of effort will result in an extremely rewarding experience serving as the basis for future microprocessor design work.
