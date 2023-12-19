# BUD - TLE project 2022

![logo_bud](https://github.com/R-oso/R-oso.github.io/assets/74653039/5e0fb1c8-705a-400a-91d0-83cd1802d53c)


## Introduction
BUD is an idea for a helpful tool that will keep track of your plants' health. The BUD software is connected to exterior hardware and both communicate with each other. This results in the software knowing when to give your specific plant more water or sunlight.

Using AI, BUD can recognize your houseplant when you open your camera on your phone. The hardware keeps track of the moist levels inside of the plant's soil and can also pick up the sun intensity. Depending on these factors, BUD might tell you to move your plant to another location or to change the amount of water the user gives to their plant.

## Table of contents
- Planning
   - Trello and Miro
   - Evaluation
- Code
  - JavaScript
    - AI (ML5 and Teachable Machine)
    - Structure
- Styling
  - Style guide
- Proof of concept

## Planning
In this project, me and three other students worked as a team. To efficiently work together we worked based on the SCRUM technique. By iterating our concept ideas and narrowing down the target audience we had in mind the idea for BUD became more viable. 

### Trello and Miro
When working with SCRUM, using a software to organize meetings and tasks is quite necessary. Trello was used for organizing tasks, and Miro was implemented as a way to come up with ideas and hold meetings with eachother. Both applications paired well with eachother and gave me a lot of learning experience about working with multiple people in one team.

### Evaluation
After each working day, we would hold a short evaluation about our current progress or struggles within the project. Planning moments to discuss and reviews is important to keep track of your progress as a team and make possible changes or additions before its too late.

## Code

### JavaScript
This project is made mostly using JavaScript. Some external software was used to create the functionality of the application.

P5 Library for compatibility with AI (ML5):

```
<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/p5.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/addons/p5.dom.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/addons/p5.sound.min.js"></script>
```

We needed to access data about each individual species of plant. After collecting data about plants and their preferred amount of sunlight and hydration, i put these statistics inside of a csv file. To parse the csv file and make the information inside of it ready to use, we decided to use PapaParse. 

 `<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.3.0/papaparse.min.js"></script>`

```
// // papa parse
function loadPlantData() {
    Papa.parse('./plantdata.csv', {
        download: true,
        header: true,
        dynamicTyping: true,
        complete: results => searchPlant(results.data)
    })
}
```
### AI (ML5 and Teachable Machine)
I chose to use both ML5 and Teachable Machine. ML5 made it possible to classify video in real-time and recognize what type of plant the user is looking at with their phone. To make this classifying system work, we needed an actual AI model that could differentiate different species of plants, based on the characteristics of each plant. Thats where Teachable Machine stepped in; a tool made by Google to make AI models in a quick manner. 

Teachable machine model link:
`let modelURL = "https://teachablemachine.withgoogle.com/models/VdFvMP0WA/";`

### Structure
Users can add their own plants to the BUD application. 

_1_
The user presses the button to add a new plant.

![WhatsApp Image 2022-06-15 at 9 31 36 AM](https://github.com/R-oso/R-oso.github.io/assets/74653039/3729e4e0-9a7e-46e7-a699-e6eba65bdae9)

_2_
The camera opens up and shows a live feed inside of the browser. The user needs to focus their camera onto the desired plant. The code will now classify the plant using ML5 and the model made with Teachable Machine. _Note: the feed only gets classified if a plant is on the screen_

![WhatsApp Image 2022-06-15 at 2 50 59 PM](https://github.com/R-oso/R-oso.github.io/assets/74653039/607faf74-cc20-4843-83f2-4a12206b8325)

_3_
The plant has been added to the homescreen. Using the CSV file, the code now matches the classified plant with the information available in the CSV. The code also picks up live data from the external hardware. This information is now used to compare the desired hydration and sun levels with the _actual_ one and gives feedback according to the results.

![WhatsApp Image 2022-06-15 at 9 31 40 AM](https://github.com/R-oso/R-oso.github.io/assets/74653039/430b0f92-b7f1-47f1-a39b-6da278b05946)

## Styling
The styling for this project was done using simple base CSS, without any libraries or other third party software.

### Styleguide

![styleguide_bud_Tekengebied 1](https://github.com/R-oso/R-oso.github.io/assets/74653039/2c00c952-ce7a-4a1b-9715-81397c317831)

# Proof of concept
This repo is made for testing the software of BUD and its compatibility with different devices.  


