1. **Check 'BELNR' in IDoc**  
   - Use the following parameters:  
     - `idoc_id`: 9876543  
     - `segment`: E1EDKA1  
     - `key`: SUPPLIER_ID  
   - SEGMENT 'E1EDP01' KEY 'BELNR'

2. **Determine if BELNR is unknown**  
   - Proceed to the next step.

3. **If 'BELNR' is 'UNKNOWN':**  
   - **Fetch BELNR ID for IDoc**  
     - Function: RFC  
     - Parameters:  
       - `function`: RFC_READ_TABLE  
       - `rfc_parameters`: {'TABLE_NAME': 'ORDERS', 'IDOC_ID': '<idoc_id>'}  
   - **Set IDoc 'BELNR' to the 'BELNR' from the RFC table**  
     - Use the following parameters:  
       - `function`: GET_SUPPLIER_DATA  
       - `rfc_parameters`: {"ORDER_NUMBER": "9876543"}  
     - SEGMENT: 'E1EDP01' KEY 'BELNR' VALUE: <belnr_from_RFC_table>  
   - **Reinitialize IDoc**  
     - Use the following parameter:  
       - `idoc_id`: 9876543  

4. **Else:**  
   - Proceed to the next step.

5. **End Process**