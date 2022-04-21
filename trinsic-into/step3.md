Leveraging templates to interact with credentials is powerful. It lets us define ahead of time how we want the credential to look, what fields are required, and enables us to simply provide values during issuance rather than some large and complicated json blob.

Let's create one now!

Template are essentially just a json list of attributes:

<pre>
    <code class="JSON">
{
    "firstName": {
      "description": "First Name",
      "optional": true
    },
    "credentialType": {
      "description": "Credential Type",
      "optional": false
    },
    "lastName": {
      "description": "Last Name",
      "optional": true
    },
    "credentialIssuer": {
      "description": "Credential Issuer",
      "optional": false
    }
  }
  </code>
</pre>

We've already uploaded some values for you:

`cat templ.json`{{execute}}

Let's create that template in our newly minted ecosystem:

`trinsic template create --name 'Trinsic CLI Master' --fields-file './templ.json'`{{execute}}

Once the template is created you will see the full template returned, which will include context and schema uri.

Notice the template ID: it was created inside the ecosystem we crated in the last step: `urn:template:<ecosystem ID>:trinsic-cli-master`. We reference this id when we issue credentials, which we will do in the next step!