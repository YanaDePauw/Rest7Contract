# Versioning endpoints

[Back to the list of all defined endpoints](endpoints.md)

This endpoint represents a single version, matching a single item.

Whether a version is accessible depends on `versioning.item.history.view.admin` configuration.  
If this is set to true, the version can only be retrieved if the user is an admin of the related item

## Create version

TODO

## Get single version

**GET /api/versioning/versions/<:versionId>**

Provide version information for the version id.

```json
{
  "id": "102",
  "version": "2",
  "type": "version",
  "created": "2015-11-03T09:44:46.617",
  "summary": "Fixing some typos in the abstract",
  "_links": {
    "versionhistory": {
      "href": "https://dspace7.4science.it/dspace-spring-rest/api/versioning/versionhistories/10"
    },
    "self": {
      "href": "https://dspace7.4science.it/dspace-spring-rest/api/versioning/versions/101"
    },
    "eperson": {
      "href": "https://dspace7.4science.it/dspace-spring-rest/api/versioning/versions/101/eperson"
    },
    "item": {
      "href": "https://dspace7.4science.it/dspace-spring-rest/api/versioning/versions/101/item"
    }
  }
}
```

Status codes:
* 200 OK - if the version exists and is accessible by the current user
* 401 Unauthorized - if you are not authenticated and versioning is not public
* 403 Forbidden - if you are not logged in with sufficient permissions and versioning is not public
* 404 Not found - if the version doesn't exist

## Get single version for item

**GET /api/core/items/{:item-uuid}/version**

See [the item endpoint](items.md#get-single-version-for-item)

## Remove version

TODO

## Update version

TODO

## Linked entities

### Version History

Retrieves the relation versions, for details see [Version history](versionhistory.md)

### EPerson

The [EPerson](epersons.md) who created the version

### Item

The [Item](items.md) matching this specific version
