const sdk = require('node-appwrite');

const client = new sdk.Client()
    .setEndpoint('https://cloud.appwrite.io/v1') // Your API Endpoint
    .setProject('<YOUR_PROJECT_ID>'); // Your project ID

const account = new sdk.Account(client);

const result = await account.createMagicURLToken(
    '<USER_ID>', // userId
    'email@example.com', // email
    'https://example.com', // url (optional)
    false // phrase (optional)
);