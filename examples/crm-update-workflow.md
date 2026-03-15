# example: crm update workflow

## goal
update a contact record after a qualifying event.

## wrong pattern
- agent calls an integration step
- agent assumes success from intermediate logs
- contact record never changes

## right pattern
- perform the update
- inspect the contact record directly
- compare expected fields with actual fields
- report complete only after exact match
