# Google Cloud Firestore Emulator

A [Google Cloud Firestore Emulator](https://cloud.google.com/sdk/gcloud/reference/beta/emulators/firestore/) container image. The image is meant to be used for creating an standalone emulator for testing.

## Quickstart

```BASH
docker run \
  --name firestore-emulator \
  -e "FIRESTORE_PROJECT_ID=project-test" \
  -p 8080:8080 \
  -d \
  xtrctio/firestore-emulator-docker
```

## Environment

The following environment variables must be set:

- `FIRESTORE_PROJECT_ID`: The ID of the Google Cloud project for the emulator.

## Networking

The emulator listens on port `8080`

## Connect application with the emulator

The following environment variables need to be set so your application connects to the emulator instead of the production Cloud Firestore environment:

- `FIRESTORE_EMULATOR_HOST`: The listen address used by the emulator (ie. `firestore-emulator:8080`)
- `FIRESTORE_PROJECT_ID`: The ID of the Google Cloud project used by the emulator.
