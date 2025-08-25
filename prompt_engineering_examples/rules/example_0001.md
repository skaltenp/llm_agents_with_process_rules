1. Retrieve 'LGORT' from Segment 'E1EDP01' in IDoc.

2. Get storage locations from SAP.

3. Determine whether storage location does exist in SAP.

4. If LGORT exists in SAP storage locations:
   - Send email to Error Handler and request manual help.
     - To: error.handler1@company.com
     - Subject: LGORT of IDoc <idoc_id> exists
     - Content: Request for help with IDoc <idoc_id>

5. Else:
   - Create storage location with id LGORT.
   - Reinitialize IDoc.
   - Inform warehouse manager about new storage location.
     - To: warehouse.manager@company.com
     - Content: Created new storage location <LGORT>