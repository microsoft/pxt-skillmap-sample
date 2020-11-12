# sample
* name: Sample MakeCode Skillmaps
* description: This is a collection of sample MakeCode Skillmaps
* infoUrl: /docs/educator-info


## map1
* name: First Skill Map
* description: A three step MakeCode Skillmap

### map1-activity1

* name: Activity 1
* type: tutorial
* description: A tutorial activity that will grant an "easy" tag when completed
* url: github:https://github.com/microsoft/pxt-skillmap-sample/blob/main/tutorials/map1/activity1.md
* tags: easy
* next: map1-activity2

### map1-activity2

* name: Activity 2
* type: tutorial
* description: A tutorial activity that will grant an "easy" tag when completed
* url: github:microsoft/pxt-skillmap-sample/tutorials/map1/activity2
* tags: easy
* next: map1-activity3

### map1-activity3

* name: Activity 3
* type: tutorial
* description: A tutorial activity that will grant an "easy" tag when completed
* url: github:microsoft/pxt-skillmap-sample/tutorials/map1/activity3
* tags: easy


## map2
* name: Second Skill Map
* description: A single step MakeCode skillmap

### map2-activity1

* name: Activity 1
* type: tutorial
* description: A tutorial activity that will grant an "coding" tag when completed
* url: github:microsoft/pxt-skillmap-sample/tutorials/map2/activity1
* tags: coding

## locked
* name: Locked Skill Map
* description: A map that is locked until you complete three easy tutorials
* required: 3 easy

### map2-activity1

* name: Activity 1
* type: tutorial
* description: A tutorial activity that will grant an "coding" tag when completed
* url: github:microsoft/pxt-skillmap-sample/tutorials/lockedmap/activity1
* tags: coding