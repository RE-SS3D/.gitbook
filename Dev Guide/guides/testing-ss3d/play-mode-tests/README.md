# Play mode tests

SS3D, now with play mode tests ! Those are heavy tests, that require building the game, and, depending on the goal, they may require starting a server, launching multiple clients ...



## Play mode tests architecture

Play mode tests need different setup based on what is tested . For instance, we might want to test picking up an item, for players embarking at the same time as host, or for players embarking after it.  We could also test it just for host.



## Manual Tests

The pages below describe a bunch of tests related to different systems implemented that a reviewer should do in order to check if everything's alright.

All tests described here should be tests that did pass at some point on the develop branch.

Please add a mention if the test you add is supposed to pass in the future but not yet.



Those tests are under the form : \


**SetUp** : What need to be done before starting the test.

&#x20;**Test** : What need to be done to execute the test.

&#x20;**Result** : The expected result.\
