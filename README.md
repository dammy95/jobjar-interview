# jobjar-interview

For this task, you will be building a basic react native app (managed by expo). The app would contain three main screens, and would also fetch data from an external api. Your work should be in a github repo with a README.md on how to run the app. No unit testing would be required.

## Create app
Create a react native app with expo: https://docs.expo.io/#quick-start
For navigation, please use react navigation: https://reactnavigation.org/

## External API
The Harvard Art Museum supplies an api for records related to art of various forms (link here: https://github.com/harvardartmuseums/api-docs).
Use axios (https://github.com/axios/axios) to retreive data from this api –– the data is then displayed on the mobile application.
Redux is a recommended library for managing application state in react and react native (https://redux.js.org/).

You should use the `API KEY` that has been given to you (https://github.com/harvardartmuseums/api-docs#curl).

## Mobile App Screens

### Splash Screen
You can configure the splash screen: https://docs.expo.io/tutorial/configuration/

![Alt text](https://github.com/dammy95/jobjar-interview/blob/main/Screenshot%202020-10-18%20at%2010.14.08.png)

### Home Screen
![Alt text](https://github.com/dammy95/jobjar-interview/blob/main/Screenshot%202020-10-18%20at%2010.15.10.png)

The home screen loads in the data from the api and renders it in a scrollable grid view. From the image above, the `title`, `primaryimageurl` (if it exists),  `displayname` of artist and `culture` of artist is shown for each art.
The necessary data can be gotten from an art record in the `records` list:
- `title`: `title`
- `primaryimageurl`: `primaryimageurl`
- `displayname`: `people[i]["displayname"]` where `i` is an index in the `people` list
- `culture`: `people[i]["culture"]` where `i` is an index in the `people` list

### Detail Screen
#### Detail Screen with no image but verification
![Alt text](https://github.com/dammy95/jobjar-interview/blob/main/Screenshot%202020-10-18%20at%2010.14.32.png)

#### Detail Screen with image but no verification
![Alt text](https://github.com/dammy95/jobjar-interview/blob/main/Screenshot%202020-10-18%20at%2010.14.49.png)

The detail screen displays more information for a specific art record as shown in the images above. The `Click for more info` button should open the default mobile browser of the user and direct them towards the `url` link. The green tick or red X is indicative of the verification of the art record. For verification you can use the `verificationlevel` field.

You should be able to navigate back to the home screen.

The necessary data can be gotten from an art record in the `records` list:
- `medium`: `medium`
- `division`: `division`
- `displayname`: `people[i]["displayname"]` where `i` is an index in the `people` list
- `provenance`: `provenance`
- `url`: `url`
- `verificationlevel`: `verificationlevel` (if 0 then art record is unverified else art record is verified)


## BONUS POINTS (not required!)
Take care of user loading state in the application. What does the user see when data is being fetched?
