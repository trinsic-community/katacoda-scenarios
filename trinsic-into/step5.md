We now that we have an issued credential, let's add it to our wallet!

in the last step we saved the credential to a file: `cred.json`. Let's look at it:

`cat cred.json`{{execute}}

To add that to our wallet, we use the insert-item command:

`trinsic wallet insert-item --item cred.json`{{execute}}

The success result will give you the unique id of the item in your wallet as a UUID urn.

Let's search through our wallet and display all the items to confirm.

Trinsic supports using SQL to pull items out of our wallet. You can filter based on fields, use offsets and limits, and much, much more! However, since we only have a single item, let's just use the default and return all items:

`trinsic wallet search`{{execute}}

This will return both the query that was executed (`SELECT c.data, c.id, c.type FROM c`) as well as an array of items currently in the wallet.