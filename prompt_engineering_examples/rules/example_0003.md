1. **Get all storage locations from SAP.**

2. **Get all materials from all storage locations.**

3. **Search for `<material_id>` in storage location.**

4. **Check if `<material_id>` exists in storage at any location:**
   - **If `<material_id>` exists:**
     1. **Set storage location ('LGORT') of IDoc to `<material_ids>` storage location.**
     2. **Reinitialize IDoc.**
   - **Else:**
     1. **Inform error handler1 that storage location does not exist.**
        - **Email: Material `<material_id>` does not exist in storage location.**
        - **To: error.handler1@company.com**