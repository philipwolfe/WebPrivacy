# WebPrivacy

Here is how I stay as private as I can while using the web.  Stay logged out of Google, Microsoft, Facebook, Twitter, and Instagram.  Don't 'log in' to your browser like Edge or Chrome.

## Browser extensions to install
(Yes, you need to trust that these extensions aren't being evil.)
 - [Adblock Plus](https://addons.mozilla.org/en-US/firefox/addon/adblock-plus/) - An extension to block the majority of ads.
 - [Code Injector](https://addons.mozilla.org/en-US/firefox/addon/codeinjector/) - An extension that enables your browser to run custom scripts based on the web domain being visited. [Source](https://github.com/Lor-Saba/Code-Injector)
 - [NoScript](https://addons.mozilla.org/en-US/firefox/addon/noscript/) - An extension that blocks all scripts with a quick toolbar button to whitelist, greylist, and blacklist domains.
 - [Cookie Autodelete](https://addons.mozilla.org/en-US/firefox/addon/cookie-autodelete/) - An extension that deletes all cookies at the end of your browsing session unless you add the domain to a whitelist.
 - [User-Agent Switcher and Manager](https://addons.mozilla.org/en-US/firefox/addon/user-agent-string-switcher/) - An extension that enables you to switch the user agent of your browser to any user agent.

### Adblock Plus
This is a highly recommended extension.  I have been a user since 2008.  After installation, locate the settings page.  Enable:
 1. Block additional tracking
 1. Block cookie warnings
 1. Block push notifications
 1. Block social media icons tracking

and disable:
 1. Allow Acceptable Ads

### Code Injector
As a user of Bing I have noticed that Bing will try to track the search results you visit by directing you to a link at bing.com before forwarding you on to your destination.  To disable this tracking, add this code for the `bing.com` domain.  Click on the Code Injector icon, and add a rule.  Then click edit and add this code will remove the event code on each search result link and make the link a direct link to the search result.
```javascript
function resetlinks()
{
    var a = document.getElementsByTagName("A");
    for(i = 0; i < a.length; i++)
    {
        var b = a[i];
        var c = b.cloneNode(true);
        c.removeAttribute("onclick");
        b.parentNode.replaceChild(c,b);
    }
}
window.setTimeout(resetlinks, 500);
```

### NoScript
NoScript is not for the faint of heart.  It disables all scripts, everywhere, making most websites unusable (and other sites, like news sites usable because they can't pop over some HTML popup).  It takes a while to get most domains set up again.  If you stick to it, you will see all the sites tracking you by the scripts that are pulled in.  On sites you don't intend to visit often you can use the handy 'Temp. TRUSTED' setting so that the site will go back to being disabled after you close the browsing session.

### Cookie AutoDelete
This is a very handy extension to remove all cookies when you close your browser.  On the sites, you want to retian the cookies, just click the button in the toolbar and add the domain to the whitelist.  Super easy.  This lets you browse as many articles as you want on some sites because the tracking cookies get cleaned out every time.

### User-agent Switcher
For more advanced scenarios when you need to change your browser to something else to get past a browser check or something.
