package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/functions"
)

func main() {
    client := client.NewClient()

    client.SetEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
    client.SetProject("<YOUR_PROJECT_ID>") // Your project ID
    client.SetKey("<YOUR_API_KEY>") // Your secret API key

    service := functions.NewFunctions(client)
    response, error := service.CreateDuplicateDeployment(
        "<FUNCTION_ID>",
        "<DEPLOYMENT_ID>",
        functions.WithCreateDuplicateDeploymentBuildId("<BUILD_ID>"),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
