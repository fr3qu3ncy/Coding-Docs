# Unity Audio Manager Documentation
=====================================

## Overview
-----------

This documentation provides an in-depth guide to creating and managing audio assets in Unity using the AudioManager script. Topics covered include setting up audio sources, playing multiple clips, background music, beat per minute (BPM) sync, and more.

## Getting Started
-----------------

### Setting Up the AudioManager Script

To get started with the AudioManager script, you'll need to create a new C# script in your Unity project. Create a new folder called "Scripts" and inside it, create a new script called `AudioManager.cs`.

```csharp
using UnityEngine;

public class AudioManager : MonoBehaviour {
    // Your audio source variables will go here...
}
```

### Setting Up Audio Sources

Before you can start playing audio clips, you need to set up your audio sources. In the Unity editor, navigate to the Hierarchy panel and create a new empty game object. Name it "AudioManager".

```csharp
public class AudioManager : MonoBehaviour {
    [Header("Music")]
    [SerializeField] private AudioSource _titleMusic;
    [SerializeField] private AudioSource _gameMusic;

    // ...
}
```

Create two audio source children objects under the AudioManager object and assign your title music and game music to them.

## Managing Audio Clips
------------------------

### Playing Multiple Clips

To play multiple clips, you can create an array of AudioClip variables in the AudioManager script. Then, you can use a loop to play each clip in the array.

```csharp
public class AudioManager : MonoBehaviour {
    private AudioClip[] _clips = new AudioClip[3];

    void Start() {
        // Load your audio clips into the array...
        foreach (AudioClip clip in _clips) {
            AudioSource.PlayClipAtPoint(clip, transform.position);
        }
    }
}
```

### Background Music

To play background music, you can use a loop to continuously play an audio clip.

```csharp
public class AudioManager : MonoBehaviour {
    private AudioClip _backgroundMusic;

    void Start() {
        // Load your background music into the variable...
        AudioSource.PlayClipAtPoint(_backgroundMusic, transform.position);
        while (true) {
            // Keep playing the background music...
        }
    }
}
```

Note: This method can be resource-intensive and may cause performance issues.

## Beat Per Minute (BPM) Sync
-----------------------------

To sync audio clips with a specific BPM, you can use the `AudioSource.pitch` property to adjust the playback speed of the clip.

```csharp
public class AudioManager : MonoBehaviour {
    private AudioClip _bpmClip;
    public float bpm = 120.0f;

    void Start() {
        // Load your bpm audio clip into the variable...
        AudioSource.PlayClipAtPoint(_bpmClip, transform.position);
        while (true) {
            // Adjust the playback speed based on the BPM...
            AudioSource.pitch = bpm / 60.0f;
            // ...
        }
    }
}
```

## Advanced Use Cases
---------------------

### Creating a Dynamic Playlist

To create a dynamic playlist that changes based on user input or game events, you can use a scripting language like C# to generate an array of audio clips and then play them in sequence.

```csharp
public class AudioManager : MonoBehaviour {
    private AudioClip[] _playlistClips;
    private int _currentClipIndex = 0;

    void Start() {
        // Generate your playlist array based on user input or game events...
        foreach (AudioClip clip in _playlistClips) {
            AudioSource.PlayClipAtPoint(clip, transform.position);
            // Wait for a short duration before playing the next clip...
        }
    }
}
```

### Creating an Interactive Music Experience

To create an interactive music experience that responds to user input or game events, you can use scripting languages like C# to generate audio clips on the fly and then play them based on user interactions.

```csharp
public class AudioManager : MonoBehaviour {
    private AudioClip _startClip;
    private AudioClip _gameplayClip;
    private AudioClip _endClip;

    void Start() {
        // Generate your start, gameplay, and end audio clips based on user input or game events...
        AudioSource.PlayClipAtPoint(_startClip, transform.position);
        while (true) {
            // Wait for user input or game events to generate new audio clips...
            if (_gameplayClip != null && _endClip != null) {
                // Play the corresponding audio clip based on the event...
                AudioSource.PlayClipAtPoint(_gameplayClip, transform.position);
            }
        }
    }
}
```

## Conclusion
----------

Creating a rich and immersive audio experience in Unity requires more than just playing background music. With the AudioManager script, you can manage your audio assets, play multiple clips, sync with beat per minute (BPM), and even create dynamic playlists or interactive music experiences.

## References
------------

* [Unity Audio Manager Documentation](https://docs.unity3d.com/Manual/script-AudioManager.html)
* [C# Scripting in Unity](https://docs.unity3d.com/Manual/CSharpScripting.html)
* [AudioSource Class Reference](https://docs.unity3d.com/ScriptReference/AudioSource.html)