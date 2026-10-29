# COMP3011 Assignment 2 - Java Local Project

For more information on this code and how to get started, see https://learn.adelaide.edu.au/courses/30747/assignments/94505

## Overview

This project extends the supplied video player with command-line options and video effects, while improving playback performance through background frame processing.

## Design

A dedicated background worker prepares video frames so that frame decoding and processing do not block the JavaFX application thread. The JavaFX thread remains responsible for updating the user interface and displaying prepared frames.

Platform.runLater() is used to schedule UI updates on the JavaFX thread. A lock protects access to shared video-grabber resources, and a playback generation counter helps prevent outdated frame-processing tasks from affecting the current playback state.

## Command-line options

The application supports command-line options for configuring playback and applying video effects. 
Run the application with --help to see the available options.

Short options can be combined, and effects can be supplied in the desired processing order.

## Running the project

The project uses Maven and JavaFX. 
In Eclipse, right-click the project and select Run As → Maven build…, then enter the appropriate Maven goal, such as:

*javafx:run*

Use the application's help output to check the available command-line arguments.

## Testing

The implementation was tested using the supplied TITAN test suite, including command-line option handling, video effects, and playback performance benchmarks.
