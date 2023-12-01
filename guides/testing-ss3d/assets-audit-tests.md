# Assets audit tests

These are edit mode tests that are intended to check **basic configuration of objects**. These represent actions that a non technical person _could_ check in the editor (given a basic checklist) without needing to look at any code. Examples include making sure no prefabs have missing scripts, making sure all tile prefabs are within a certain size range, all asset data references are not null etc.&#x20;

Asset audits have been configured as parameterized tests, so it will be immediately clear which object is causing failures.&#x20;

Note that a business rule is that test failures for prefabs should be resolved before test failures for scenes, because the scenes may be broken because the prefabs in them are broken.
