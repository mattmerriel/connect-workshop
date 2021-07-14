# Configure our First Contact Flow

## Configure our First Contact Flow

1. Firstly, we now need to browse into our Connect Instance. We can find the URL for this by browsing back to the <b>Overview</b> page of our Instance Configuration. Click the <b>Login URL</b> to continue.
![Connect Image 1](images/flow/1.png)

2. Once you've logged in we need to create our first Contact Flow (which will actualy be the second one in our actual flow but we'll ignore that for the moment). Select <b>Contact flows</b> from the <b>Routing</b> Menu.
![Connect Image 1](images/flow/2.png)

3. Next we need to click on <b>Create contact flow</b> on the right hand side
![Connect Image 1](images/flow/4.png)

4. We firstly need to give our Contact flow a name, so we'll call it <b>Menu</b>.
![Connect Image 1](images/flow/3.png)

5. now we need to bring in a menu for our customers where we will ask if they are after internet banking or wish to speak to a banking representitive. To do this we need to <b>get customer input</b>. Drag one from the <b>Interact</b> section onto the canvas.
![Connect Image 1](images/flow/5.png)

6. Clicking on <b>get customer input</b> and we can define the <b>Text-to-speech or chat text</b> we want. Go ahead and add some prompts asking the caller to press 1 or 2.
![Connect Image 1](images/flow/6.png)

7. scrolling down the page and we want to click the <b>Add another condition</b> link twice, so we can add 1 and 2 as options. Click <b>Save</b> once your done.
![Connect Image 1](images/flow/7.png)

8. Next, we'll add the second menu for those who press two. This is where we'll use the Lex Bot we configured earlier. Start off by dragging another <b>get customer input</b> block onto the canvas.
![Connect Image 1](images/flow/8.png)

9. Like before, when we open up the properties we first need to define some <b>Text-to-speech</b> for the prompt to say. This time we are asking the caller what their call is regarding.
![Connect Image 1](images/flow/9.png)

10. Here we need to select that we wish to use an <b>Amazon Lex</b> Bot and then the Bot name and the Alias. Select the <b>purposeOfCallBot</b> from the drop down menu and then the <b>TestBotAlias</b> Alias (or whatever you've got your Alias set to)
![Connect Image 1](images/flow/10.png)

11. Next we need to click on <b>Add another intent</b> three times so we can add each of the Lex intents to the list of possible outcomes. Add in <b>CreditCard</b>, <b>General</b> and <b>HomeLoan</b> and click <b>Save once your done.
![Connect Image 1](images/flow/11.png)

12. To act as placeholders, we now need to add some <b>Play Prompts</b> so that Connect can tell us which prompt we've gotten to. Drag three <b>Play Prompt</b> steps onto the canvas and connect them to the three possible outcomes (we'll address Default and Error in a moment).
![Connect Image 1](images/flow/12.png)

13. For the first prompt (the one linked to the CreditCard Intent) we set some default text and click <b>Save</b>
![Connect Image 1](images/flow/13.png)

14. For the Second prompt (the one linked to the General Intent) we tweak the text slightly and click <b>Save</b>
![Connect Image 1](images/flow/14.png)

15. For the last prompt (the one linked to the HomeLoaad Intent) we make reference to the Home Loan Team and click <b>Save</b>
![Connect Image 1](images/flow/15.png)

16. So that we can test our Contact Flow, we need to close out all of the un-routed possible solutions. To start with, Drag a <b>Disconnect</b> Step onto the canvas and wire it up to the <b>Okay</b> outputs from the previous three <b>Play prompt</b> Steps.
![Connect Image 1](images/flow/16.png)

17. Next we wire up the <b>Timeout</b> and <b>Default</b> option from our initial <b>get customer input</b> step to also point to our Lex Bot. This will ensure that all customer enquiries are at least handled, even if not in the most effectent way possible. We can come back to this at a later stage and improve the handling.
![Connect Image 1](images/flow/17.png)

18. Next we need to handle when a caller try to select <b>Option 1</b> (phone banking). So we can test our contact flow, for the moment we can just add a prompt and then route the call to the <b>General Banking</b> team. We will come back and add another <b>Contact Flow</b> to handling Phone Banking in the next Part of the workshop. For the moment, add a <b>Play Prompt</b> Step to the canvas and link it to other steps as shown below.
![Connect Image 1](images/flow/18.png)

19. For the prompt, we just add some placeholder text saying phone banking is currently unavilable. click <b>Save</b> once your done.
![Connect Image 1](images/flow/19.png)

20. Next we link the <b>Default</b> output from our Lex bot to the <b>General Banking Prompt to again make sure all customer enquiries are caught.
![Connect Image 1](images/flow/20.png)

21. Lastly, we add one final prompt to capture any error scenarios, and just like the other's we route that to the General Team as well.
![Connect Image 1](images/flow/21.png)

22. For the prompt we just add some boiler plate text and click <b>Save</b> when where done.
![Connect Image 1](images/flow/22.png)

23. With all that done, we can go ahead and <b>Save</b> our flow.
![Connect Image 1](images/flow/23.png)

24. and click <b>Save</b> to the <b>Save Flow</b> prompt.
![Connect Image 1](images/flow/24.png)

25. Next, we can go ahead and click <b>Publish</b> which will make it available to the rest of our instance.
![Connect Image 1](images/flow/25.png)

26. and click <b>Publish</b> to the popup.
![Connect Image 1](images/flow/26.png)

## Configure Dial In

1. First we want to broowse to the phone number section.
![Connect Image 1](images/flow/27.png)

2. Click <b>Claim a number</b>
![Connect Image 1](images/flow/28.png)

3. select a country, phone number and the <b>Menu</b> Contact Flow and click <b>Save</b>.
![Connect Image 1](images/flow/29.png)

4. You should now be able to ring the inbound number and navigate the menu structure. In the next section we will add [Phone Banking](Part5.md)