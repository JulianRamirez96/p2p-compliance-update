# P2P Compliance Flag Update Script

## Overview
This SQL script updates procurement compliance flags and lead information in a master spend table using P2P (Procure-to-Pay) data. It includes comprehensive data validation and QA checks to ensure data integrity.

## Features
- Updates compliance flags from P2P data
- Handles missing data with default values
- Performs data validation checks
- Generates QA reports
- Maintains data integrity with transaction management

## Tables Used
| Table Name            | Description                        |
|-----------------------|------------------------------------|
| `P2P_MASTER_ANON`     | Source P2P data                    |
| `MASTER_SPEND_BACKUP` | Original master data backup        |
| `MASTER_SPEND_FINAL`  | Working table for updates          |

## Key Operations
1. **Initial Table Setup**: Prepares working and backup tables.
2. **MERGE Operation**: Updates matched records with new compliance flags and lead info.
3. **UPDATE Operation**: Handles unmatched records, applying default values.
4. **QA Validation**: Runs checks to ensure data accuracy and completeness.

## QA Reports
| Report Name         | Purpose                                             |
|---------------------|-----------------------------------------------------|
| Spend Comparison    | Validates total spend before and after updates      |
| Results Check       | Breaks down results by fiscal month and flags       |
| Invoice Check       | Compares line items for changed records             |

## Usage
1. Ensure you have necessary permissions on all tables.
2. Execute the script in your Oracle environment.
3. Review the generated QA reports.
4. Verify data integrity using the provided checks.

## File Structure
```
UPDATE_P2P_FLAGS.sql
├── Table Creation
├── Data Update Logic
├── QA Queries
└── Export Queries
```

## Data Requirements
- Vendor/Supplier IDs
- Invoice Numbers
- Compliance Flags
- Lead Information
- Fiscal Month/Year data

## Notes
- Supports fiscal years 2024-2025.
- Default value for missing records: `'Not in P2P'`.
- Maintains audit trail through QA exports.
- Uses Oracle-specific SQL syntax.

## Best Practices
- Take a backup before running updates.
- Review QA reports thoroughly.
- Maintain source data integrity.
- Follow proper change management procedures.
