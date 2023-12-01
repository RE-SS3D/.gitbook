# 📣 Audios

In SS3D, audio uses a single class to manage most sounds, it's the audio system.

The audio system handles creating and destroying audio sources, putting those sources on the right game objects and syncing sound between clients.

In the vast majority of cases, you should never add an audio source yourself to a game object, but instead you should use the audio system.

One of its perk is that it's reusing already existing audio sources that are not playing anymore, instead of adding a new source everytime something needs to play a sound.

It's also maintaining an healthy amount of audio sources by limiting the maximum amount allowed on a single client.





## Syncing sound&#x20;

It should be noted that in order to sync sound between clients, the audio system put audio sources on game object with a network object component. This is an easy way to find the same game object on the client. However, a restriction of that solution is that you should not put more than one audio source per network object.



## Purging sound

After a while, if no sound is played, an audio source gets destroyed. This is better for performances.
