# Lab_3: .NET MAUI Note-Taking App

This is a simple note-taking application written in XAML and C# with .NET MAUI. It allows users to create, edit, and delete notes, which are saved locally on the device.

## Features

* **View All Notes**: A main page displays a collection of all saved notes, showing the note's text and the date it was last saved.
* **Create & Edit Notes**: Users can create a new note or select an existing note to open an editor page.
* **Save Notes**: Notes are saved to the device's application data directory.
* **Delete Notes**: Notes can be deleted from the editor page.
* **About Page**: Includes a simple "About" page with app information.
* **Navigation**: Uses .NET MAUI's Shell with a `TabBar` for navigation between the "Notes" and "About" pages.

## Technology Stack

* **.NET 9**
* **.NET MAUI**
* **C# & XAML**
* **MVVM Pattern**: Utilizes the Model-View-ViewModel pattern.
    * **CommunityToolkit.Mvvm**: Used for `ObservableObject` and `AsyncRelayCommand` implementations.
* **Cross-platform**: Targets Android, iOS, MacCatalyst, and Windows.

## Project Structure

Here is a brief overview of the key files and directories in the project:

* **/Models/Notes.cs**: Contains the `Notes` model. This class includes the logic for saving, deleting, loading a single note, and loading all notes from the file system.
* **/ViewModels/**:
    * `NotesViewModel.cs`: Manages the collection of all notes (`ObservableCollection`) and handles commands for creating new notes and selecting existing ones.
    * `NoteViewModel.cs`: Manages the state and commands (`SaveCommand`, `DeleteCommand`) for a single note being edited.
    * `AboutViewModel.cs`: Provides data and commands for the `AboutPage`.
* **/Views/**:
    * `AllNotesPage.xaml`: The main page that displays the list of all notes in a `CollectionView`.
    * `NotePage.xaml`: The page used for creating and editing a note, containing an `Editor` and "Save"/"Delete" buttons.
    * `AboutPage.xaml`: The page that displays information about the app.
* **App.xaml.cs**: The main application entry point.
* **AppShell.xaml.cs**: Configures the app's navigation shell, including the `TabBar` and routing for the `NotePage`.
* **MauiProgram.cs**: Configures and builds the .NET MAUI application, including registering custom fonts.

## Getting Started

### Prerequisites

* .NET 9 SDK
* .NET MAUI Workload (install via the Visual Studio Installer or `dotnet workload install maui`)

### Running the Application

1.  Clone the repository.
2.  Open the solution in Visual Studio 2022 (or your preferred IDE).
3.  Select your target platform (e.g., Android, iOS, Windows) and run the project.

Alternatively, you can use the .NET CLI:

```bash
# Restore dependencies
dotnet restore

# Build the project (example for Android)
dotnet build -t:Run -f net9.0-android

# Build the project (example for iOS)
dotnet build -t:Run -f net9.0-ios
