# Hourglass

Where did all that time go? Hourglass just like its name, is a prototype for an app that revolves around the time management of screen-time for its users. The application will feature compatibilty with other installations on the device such as social media platforms - where once clicking on a slected app, a timer will appear with an hourglass icon accrording to the run time of opening. Users will be able to customise features such as wanted apps to be utilised, limits, loops, and aesthetics such as a colour palette. This prototype was developed according to personal experiences, and aims to be accessible for users of all ages and abilties. 

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Features](#features)
* [Setup](#setup)
* [Project Status](#project-status)
* [Acknowledgements](#acknowledgements)
* [Sources of prototype](#sources of prototype)
* [Appendix](#appendix) 
<!-- * [License](#license) -->


## General Information
Hourglass is a prototype for an app that revolves around the time management of its users. The application will feature compatibility with others on the device such as social media platforms -- where once clicking on a slected app, a timer will appear with an hourglass icon according to the run time of opening. Users will be able to customise features such as wanted apps to be utilised, limits, loops, and aesthetic via a colour palette. This prototype aims to be accessible for users of all ages and abilties. 

The prototype intends to assist in the time managememt of its users, ultimately combating procastination, and encouraging time efficiency.

With a timer that is visible alongside the open selected app, this prototype has the purpose of assisting users who may have difficulty in managing time or need extra support in doing so. For those who have a busy day ahead, the night owls who continuously scroll, or simply for a reminder - this project is made for everyone. 

This specific idea was undertaken due to personal experinces. As somebody who sometimes struggles with managing time on screens, this prototype was created to further improve on "app limits" built-in iphones. Using this solves most typical problems, however a number of improvements were made:
- A password to be entered and changed via email (difficult to bypass promised time)
- Aesthetic customisation for users
- Real-time visible timer
<!-- You don't have to answer all the questions - just the ones relevant to your project. --> 


## Technologies Used
- X Code 16

## Features
List the ready features here:
- Live simulator 
- iphone suulation of prototype
- Clear errors and occasional assists e.g. "fix"





## Setup
- Download Xcode
- Run simulator
- Enter in code





## Project Status
Project is:  _complete_ 




## Acknowledgements
This project was inspired by my personal experince of using Apple's screentime app limits feature. Originally great for exam periods and stud purposes, after learning quickly about bypassing it became easy to ignore time limits. I would like to acknowledge Apple and its screentime feature in setting up the idea as a framework to further build upon with my ideas. 


## Sources of prototype
Image Color Picker. (2024). RGB Color Picker Online. Image Color Picker. https://www.imgcolorpicker.com/rgb-color-picker 




## Appendix
Input: "Could you please help me create a basic SwiftUI app with a password check?"
Output: import SwiftUI

@main
struct HourglassApp: App {
    var body: some Scene {
        WindowGroup {
            ContentView() // Entry point for your app
        }
    }
}

struct ContentView: View {
    @State private var showPasswordPrompt = false
    @State private var isAuthenticated = false
    @State private var passwordInput = ""

    var body: some View {
        ZStack {
            Color.white.ignoresSafeArea() // Placeholder background, customize as needed

            if isAuthenticated {
                MainMenuView() // Main menu view after authentication
            } else {
                Text("Welcome to Hourglass")
                    .font(.largeTitle)
                    .padding()
                    .onAppear {
                        DispatchQueue.main.asyncAfter(deadline: .now() + 1) {
                            showPasswordPrompt = true
                        }
                    }
            }
        }
        .alert("Enter Password", isPresented: $showPasswordPrompt, actions: {
            TextField("Password", text: $passwordInput)
            Button("Submit") {
                if passwordInput == "uts123" { // Your defined password
                    isAuthenticated = true
                    showPasswordPrompt = false
                } else {
                    passwordInput = "" // Clear input on incorrect entry
                }
            }
            Button("Cancel", role: .cancel) {
                showPasswordPrompt = false
            }
        }, message: {
            Text("Please enter the password to proceed.")
        })
    }
}

struct MainMenuView: View {
    var body: some View {
        VStack {
            Text("Main Menu")
                .font(.largeTitle)
                .padding()
            // Add buttons and customization options here
        }
    }
}

Input: ForEach(MenuOption.allCases, id: \.self) { option in giving error
Output: enum MenuOption: String, CaseIterable {
    case apps = "Apps"
    case limits = "Limits"
    case loops = "Loops"
    case customisation = "Customisation"
}
Input: errors in my code what's the basic layout it should look like? Am i doing it in the wrong order?
Output: @main
struct YourAppName: App {
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}

