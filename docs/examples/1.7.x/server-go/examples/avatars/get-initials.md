package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/avatars"
)

func main() {
    client := client.New(
        client.WithEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
        client.WithProject("<YOUR_PROJECT_ID>") // Your project ID
        client.WithSession("") // The user session to authenticate with
    )

    service := avatars.New(client)
    response, error := service.GetInitials(
        avatars.WithGetInitialsName("<NAME>"),
        avatars.WithGetInitialsWidth(0),
        avatars.WithGetInitialsHeight(0),
        avatars.WithGetInitialsBackground(""),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
