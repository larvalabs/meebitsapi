# Meebits API

This repository is the home of documentation for the API for the [Meebits](https://meebits.larvalabs.com/). The current focus is allowing access to Meebit model files for use in any game, social platformn, or metaverse a Meebit owner wants to enter. It will likely expand in the future to allow access to Meebit attribute and market data.

# Meebits Owner Files API (Alpha)

This API will allow third party access to additional files for Meebits, if the owner gives permission. Current examples of additional files include T-Pose VOX files, and rigged models in VRM, FBX and GLB formats. More detail on these formats in the release [Tweet thread](https://twitter.com/larvalabs/status/1455644953204469760).

## Requesting Owner Permission

To grant access a Meebit owner will sign a message on our site, and then we will redirect to a call back URL and provide an access token and account. The flow is started by going to a URL of the format:

```
https://meebits.larvalabs.com/meebits/apiAccessRequest?callbackUrl=[url_encoded_callback_to_your_site]
```

For example, here is a link that includes a test callback on our own site that will show the results of the request: [https://meebits.larvalabs.com/meebits/apiAccessRequest?callbackUrl=https%3A%2F%2Fmeebits.larvalabs.com%2Fmeebits%2FtestCallback](https://meebits.larvalabs.com/meebits/apiAccessRequest?callbackUrl=https%3A%2F%2Fmeebits.larvalabs.com%2Fmeebits%2FtestCallback)

## Response Options

If the access request was completed successfully you will receive two parameters to your callback URL:
```
account: The account address that apporved access.
accessToken: The token that grants access to the owner files.
```

If there was an error or the user cancelled the request you will receive the following parameter to your callback URL:
```
errorMessage: The message describing the error that occured, or that the user declined access.
```

## API and File Access

At the moment there is only a single endpoint available:

```
https://meebits.larvalabs.com/api/v1/account/[account_address]
```

Which will return a response that looks like the following:
```json
{
  "statusCode": 200,
  "data": {
    "address": "0xC352B534e8b987e036A93539Fd6897F53488e56a",
    "meebits": [
      {
        "index": 47,
        "type": "HUMAN",
        "imageUrl": "/meebitimages/characterimage?index=47&type=full&imageType=jpg",
        "minted": true,
        "owner": {
          "address": "0xC352B534e8b987e036A93539Fd6897F53488e56a"
        },
        "ownerDownloadVox": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=false&file=vox&index=47",
        "ownerDownloadVoxTPose": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox_filled&index=47",
        "ownerDownloadVoxTPoseCored": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox&index=47",
        "ownerDownloadVox3DPrint": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=print&index=47",
        "ownerDownloadVRM": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vrm&index=47",
        "ownerDownloadFBX": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=fbx&index=47",
        "ownerDownloadGLB": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=glb&index=47"
      },
      {
        "index": 148,
        "type": "HUMAN",
        "imageUrl": "/meebitimages/characterimage?index=148&type=full&imageType=jpg",
        "minted": true,
        "owner": {
          "address": "0xC352B534e8b987e036A93539Fd6897F53488e56a"
        },
        "ownerDownloadVox": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=false&file=vox&index=148",
        "ownerDownloadVoxTPose": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox_filled&index=148",
        "ownerDownloadVoxTPoseCored": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox&index=148",
        "ownerDownloadVox3DPrint": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=print&index=148",
        "ownerDownloadVRM": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vrm&index=148",
        "ownerDownloadFBX": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=fbx&index=148",
        "ownerDownloadGLB": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=glb&index=148"
      },
      {
        "index": 151,
        "type": "HUMAN",
        "imageUrl": "/meebitimages/characterimage?index=151&type=full&imageType=jpg",
        "minted": true,
        "owner": {
          "address": "0xC352B534e8b987e036A93539Fd6897F53488e56a"
        },
        "ownerDownloadVox": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=false&file=vox&index=151",
        "ownerDownloadVoxTPose": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox_filled&index=151",
        "ownerDownloadVoxTPoseCored": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox&index=151",
        "ownerDownloadVox3DPrint": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=print&index=151",
        "ownerDownloadVRM": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vrm&index=151",
        "ownerDownloadFBX": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=fbx&index=151",
        "ownerDownloadGLB": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=glb&index=151"
      },
      {
        "index": 184,
        "type": "HUMAN",
        "imageUrl": "/meebitimages/characterimage?index=184&type=full&imageType=jpg",
        "minted": true,
        "owner": {
          "address": "0xC352B534e8b987e036A93539Fd6897F53488e56a"
        },
        "ownerDownloadVox": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=false&file=vox&index=184",
        "ownerDownloadVoxTPose": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox_filled&index=184",
        "ownerDownloadVoxTPoseCored": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vox&index=184",
        "ownerDownloadVox3DPrint": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=print&index=184",
        "ownerDownloadVRM": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=vrm&index=184",
        "ownerDownloadFBX": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=fbx&index=184",
        "ownerDownloadGLB": "https://meebits.larvalabs.com/meebits/ownerdownload?tpose=true&file=glb&index=184"
      },
      ...
      ]
  }
}
```

To access the owner files take the provided URL and append your access token received above like this: `&accessToken=[access_token]`. If the token is valid the download will proceed.

## Token Expiry

All tokens have a 24 hour expiry placed on them for now, so download the files you need and cache them on your side.
