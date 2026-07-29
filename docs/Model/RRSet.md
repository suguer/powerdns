# RRSet

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** | Name for record set (e.g. “www.powerdns.com.”) |
**type** | **string** | Type of this record (e.g. “A”, “PTR”, “MX”) |
**ttl** | **int** | DNS TTL of the records, in seconds. MUST NOT be included when changetype is set to “DELETE”. |
**changetype** | **string** | MUST be added when updating the RRSet. Must be one of DELETE, EXTEND, PRUNE or REPLACE. With DELETE, all existing RRs matching name and type will be deleted, including all comments. With EXTEND, only a single record shall be present, and it will be added to the RRSet if not already present. With PRUNE, only a single record shall be present, and it will be deleted from the RRSet if present. With REPLACE, when records is present, all existing RRs matching name and type will be deleted, and then new records given in records will be created. If no records are left, any existing comments will be deleted as well. When comments is present, all existing comments for the RRs matching name and type will be deleted, and then new comments given in comments will be created. | [optional]
**records** | [**\OpenAPI\Client\Model\Record[]**](Record.md) | All records in this RRSet. When updating Records, this is the list of new records (replacing the old ones). Must be empty when changetype is set to DELETE, and must contain only one element when changetype is set to EXTEND or PRUNE. An empty list results in deletion of all records (and comments). |
**comments** | [**\OpenAPI\Client\Model\Comment[]**](Comment.md) | List of Comment. Must be empty when changetype is set to DELETE, EXTEND or PRUNE. An empty list results in deletion of all comments. modified_at is optional and defaults to the current server time. | [optional]
**write_unchanged** | **bool** | In the case of a PRUNE or EXTEND operation, specifies whether a database update should be performed even if the operation does not change the RRSet, causing the modification timestamp to be updated if the backend supports it. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
