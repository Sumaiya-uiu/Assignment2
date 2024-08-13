1. Load and preprocess data:
   - Load pharmacy data, salesperson distance data, UK district data
   - Assign None to salesperson column in pharmacy data
   - Create clinic_locations dictionary

2. Initial setup:
   - Drop unnecessary columns from pharmacy data
   - Check if all clinic districts are available in the map
   - Assign initial clinics to salespeople (assign_initial_neighbours function)

3. Create pharmacy_matrix:
   - Group pharmacy data by district
   - Sum numeric columns
   - Set initial salesperson assignments

4. Create initial balance_matrix and balance_matrix_result

5. Display initial balance matrix visuals

6. Create initial map with salespersons' home territories

7. Main assignment loop:
   WHILE there are unassigned districts in pharmacy_matrix:
       a. Find unoccupied neighbor districts with clinics:
          - Get currently assigned districts for each salesperson
          - Find neighboring districts that can be assigned next
          - Filter out occupied and non-adjacent districts

       b. Calculate clinic count and distance for potential assignments

       c. Determine next salesperson and district to assign:
          - Rank salespersons based on neighbor segment priority
          - Rank salespersons based on balance matrix
          - Choose assignment based on clinic count, segment priority, and balance

       d. Assign chosen district to chosen salesperson:
          - Update pharmacy_data
          - Update pharmacy_matrix
          - Update balance_matrix

       e. Update map with new assignment

       f. Increment assignment count

8. Save results:
   - Save pharmacy_data to CSV
   - Save pharmacy_matrix to CSV
   - Save map to HTML file