Let's go ahead and issue a credential using the template we just created.

The first thing you will need is the full template id:

`trinsic template list`{{execute}}

Find the ID of the `Trinsic CLI Master` template we just created. It will be in the form of a urn:

`urn:template:<ecosystem ID>:trinsic-cli-master`

Now, let's define the values we want to populate the credential with. You can provide these as a json string or, more easily, in a json file. We've pre-populated one for you, update it with any values you want:

`nano values.json`{{execute}}

When you are done, close the editor and save your values with <kbd>Ctrl</kbd>+<kbd>X</kbd>


Finally let's issue the credential. Copy and paste this into the terminal, then fill in your template ID from above:

`trinsic vc issue-from-template --values-file './values.json' --out cred.json --template-id `{{copy}}

Congratulations! You just issued your first credential in your ecosystem! Now let's add it to our wallet!