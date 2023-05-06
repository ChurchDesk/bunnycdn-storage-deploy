# bunnycdn-storage-deploy

This action deploys selected directory to BunnyCDN storage.

## Inputs

### `source`

**Required** The source directory folder.

### `storageZoneName`

**Required** The name of your storage zone where you are connecting to.

### `accessKey`

**Required** The storage API key.

### `storageEndpoint`

The storage endpoint. Default value is storage.bunnycdn.com

### `storagePassword`

The storage password. It should be read and write capable.

### `pullZoneId`

Necessary for purging pull zone.

### `purge`

It will purge the pull zone if true. pullZoneId and pullZoneAccessKey should be provided.

### `remove`

It will remove the files from storage before uploading if "true" provided.

## Example usage

```
- name: Deploy to BunnyCDN
  uses: ayeressian/bunnycdn-storage-deploy@v1.1.6
  with:
    source: "dist"
    storageZoneName: "${{ secrets.STORAGE_NAME }}"
    storagePassword: "${{ secrets.STORAGE_PASSWORD }}"
    accessKey: "${{ secrets.STORAGE_KEY }}"
    pullZoneId: "${{ secrets.ZONE_ID }}"
    remove: "true"
    purge: "true"
```
