# chromePasswordDeletor
Small JS that deletes all stored passwords of your google chrome browser<br/>

so if you want to delete all the passwords of your google chrome browser this often doesnt work with the solutions given by the google community. A save way is to do it yourself, by deleting each password one after another. Google doesnt provide a button there that delete all passwords at once......<br/>
This can be very cumbersome if you got more than a handful of passwords.<br/>
The following small javascript will imitate you scrolling through all you passwords and delete them for you automatically:<br/>
<br/>
open chrome and go to URL     chrome://settings/passwords<br/>
<br/>
open the dev tools with F12 and open the console tab.<br/>
<br/>
insert the following code and press Enter:<br/>
<br/>
```
nodelist = document.querySelector("body > settings-ui").shadowRoot.querySelector("#main").shadowRoot.querySelector("settings-basic-page").shadowRoot.querySelector("#basicPage > settings-section.expanded > settings-autofill-page").shadowRoot.querySelector("#passwordSection").shadowRoot.querySelector("#passwordsListHandler > div > div.cr-separators.list-with-header").childNodes;

//length minus 1 or smaller than because last element is no password
for(let count = 0; count < nodelist.length; count++){
    nodelist[count].shadowRoot.querySelector("#moreActionsButton").click();
    document.querySelector("body > settings-ui").shadowRoot.querySelector("#main").shadowRoot.querySelector("settings-basic-page").shadowRoot.querySelector("#basicPage > settings-section.expanded > settings-autofill-page").shadowRoot.querySelector("#passwordSection").shadowRoot.querySelector("#passwordsListHandler").shadowRoot.querySelector("#menuRemovePassword").click();
    console.log("deleted");
}
```
<br/>
after some seconds all you passwords are deleted one by one : )
