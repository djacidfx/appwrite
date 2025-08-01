package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/sites"
)

func main() {
    client := client.New(
        client.WithEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
        client.WithProject("<YOUR_PROJECT_ID>") // Your project ID
        client.WithKey("<YOUR_API_KEY>") // Your secret API key
    )

    service := sites.New(client)
    response, error := service.GetDeployment(
        "<SITE_ID>",
        "<DEPLOYMENT_ID>",
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
