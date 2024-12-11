from appwrite.client import Client

client = Client()
client.set_endpoint('https://cloud.appwrite.io/v1') # Your API Endpoint
client.set_project('<YOUR_PROJECT_ID>') # Your project ID
client.set_key('<YOUR_API_KEY>') # Your secret API key

messaging = Messaging(client)

result = messaging.create_push(
    message_id = '<MESSAGE_ID>',
    title = '<TITLE>',
    body = '<BODY>',
    topics = [], # optional
    users = [], # optional
    targets = [], # optional
    data = {}, # optional
    action = '<ACTION>', # optional
    image = '[ID1:ID2]', # optional
    icon = '<ICON>', # optional
    sound = '<SOUND>', # optional
    color = '<COLOR>', # optional
    tag = '<TAG>', # optional
    badge = '<BADGE>', # optional
    draft = False, # optional
    scheduled_at = '' # optional
)