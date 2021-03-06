## Running Tests on Travis

[Travis](https://travis-ci.org/) automatically runs tests whenever a github
repo changes.  To have Travis automatically run tests on your forked copy
of this repo:

1.  Fork this repo on [GitHub](https://github.com/).
1.  Visit the
    [Google Developers Console](https://console.developers.google.com/) and
    choose an existing project or create a new project.
1.  Under `APIs & auth`, choose Credentials.
1.  Click `Add credentials`, and then click `Service account`.
1.  Under `Key type`, choose `JSON`, and then click `Create`.  A json credential
    file will be downloaded to your computer.
1.  Under `APIs & auth`, enable Cloud Datastore API.
1.  Go to `Firestore` in the Console and select "Firestore in Native Mode"
1.  Visit [Travis](https://travis-ci.org/profile ) and turn on Travis for your
    new forked repo.
1.  Go back to the [Travis](https://travis-ci.org/) home page, click on your
    repo, then click on `Settings`.
1.  Under Environment Variables, set the following envvars:
    - `GOOGLE_CLOUD_PROJECT`

    **Be sure te leave `Display value in build log` switched OFF for
      secret values.**

1.  Base-64 encode the json file you downloaded in step 5.  On unix machines,
    this can be done with a command like
    `base64 -w 0 < my-test-bf4af540ca4c.json`.
1. Under Environment Variables, set GOOGLE_CREDENTIALS_BASE64 to the
    base64-encoded json from step 9.  **Be sure te leave `Display value in build
    log` switched OFF.**
