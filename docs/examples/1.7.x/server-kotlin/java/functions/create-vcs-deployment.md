import io.appwrite.Client;
import io.appwrite.coroutines.CoroutineCallback;
import io.appwrite.services.Functions;
import io.appwrite.enums.VCSDeploymentType;

Client client = new Client()
    .setEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
    .setProject("<YOUR_PROJECT_ID>") // Your project ID
    .setKey("<YOUR_API_KEY>"); // Your secret API key

Functions functions = new Functions(client);

functions.createVcsDeployment(
    "<FUNCTION_ID>", // functionId
    VCSDeploymentType.BRANCH, // type
    "<REFERENCE>", // reference
    false, // activate (optional)
    new CoroutineCallback<>((result, error) -> {
        if (error != null) {
            error.printStackTrace();
            return;
        }

        System.out.println(result);
    })
);

