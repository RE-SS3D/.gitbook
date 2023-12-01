# 🔗 Gitbook and Github syncing

Gitbook and Github are automatically syncing, at for all of our current spaces. The syncing allow us to have a backup of our gitbook data in case of a catastrophic lost. Any space added later will need to be configured to sync.

{% hint style="warning" %}
* Do NOT enable the "Install on all spaces" option in the integration menu. It will break the current integrations and mess up a bunch (made this mistake once already). Each space must be enabled individually.
* Do NOT modify files directly on github unless you know what you're doing! It syncs BOTH ways!&#x20;
{% endhint %}

If you add another space, follow the doc here to sync it \
\
[https://docs.gitbook.com/integrations/git-sync/enabling-github-sync](https://docs.gitbook.com/integrations/git-sync/enabling-github-sync)

When syncing another space, don't let the root folder by default, otherwise it'll make a mess on github.&#x20;

Add a folder with a similar name to the space you created.

For this space, here's the project directory

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
