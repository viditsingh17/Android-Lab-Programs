# Content Providers
A content provider manages access to a central repository of data. A provider is part of an Android application, which often provides its own UI for working with the data. However, content providers are primarily intended to be used by other applications, which access the provider using a provider client object. Together, providers and provider clients offer a consistent, standard interface to data that also handles inter-process communication and secure data access.

## Problem Statement
Write a program to create an activity with two text boxes (date /time and note contents). Create a content provider to store the date and time and note contents to the database. Create another program with a Button (Fetch Today Notes) on press must access the note provider and display the notes stored for today’s date.

## Screenshots
### Notes Saver
![Alt text](screenshots/3a.png?raw=true)
![Alt text](screenshots/3b.png?raw=true)
![Alt text](screenshots/3c.png?raw=true)
![Alt text](screenshots/3d.png?raw=true)
### Notes Viewer
![Alt text](screenshots/3e.png?raw=true)
![Alt text](screenshots/3f.png?raw=true)
![Alt text](screenshots/3g.png?raw=true)

## Setup
There are 2 Apps required to demonstrate content providers.
1. Note Saver
2. Notes Viewer

### Notes Saver
1. Create a New Android Project by the name **Notes Saver** and resulting package name **com.bharathksunilk.notes.saver**
2. Let the App have an Activity, copy contents of [activity_main.xml](xml/NotesSaver/activity_main.xml) and [MainActivity.java](java/com/bharathksunilk/notes/saver/MainActivity.java)
3. Create a java class [DBHandler.java](java/com/bharathksunilk/notes/saver/DBHandler.java) for managing Database.
4. Create a java class [NotesProvider.java](java/com/bharathksunilk/notes/saver/NotesProvider.java) which will be our content provider.
5. Update the AndroidManifest:
```
<provider
android:name=".NotesProvider"
android:authorities="com.bharathksunilk.notes"
android:exported="true" />
```

### Notes Viewer
1. Create a New Android Project by the name **Notes Viewer** and resulting package name **com.bharathksunilk.notes.viewer**
2. Let the App have an Activity, copy contents of [activity_main.xml](xml/NotesViewer/activity_main.xml) and [MainActivity.java](java/com/bharathksunilk/notes/viewer/MainActivity.java)

## Run
Run the Notes Saver application first and enter dates as dd/MM/yyyy and the contents. After which run the Notes Viewer app, click the button and you will recieve notes for today if you have saved any
#### NOTE: 
We haven't included empty EditText Checks yet.