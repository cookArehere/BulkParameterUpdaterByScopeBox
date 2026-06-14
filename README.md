# BulkParameterUpdaterByScopeBox

A powerful and flexible **Dynamo/Python script for Autodesk Revit** that automates the process of writing parameter values to elements based on their spatial location within a specific **Scope Box** and custom parameter filters.

This tool is highly efficient for BIM Managers, MEP Coordinators, and VDC Engineers who need to automate zoning, phasing, or system classification tasks without manual selection.

## 🚀 Features

- **Spatial Filtering**: Automatically detects elements located inside a selected Revit **Scope Box** using fast geometric bounding box calculations via Revit API.
- **Dual-Mode Filtering**:
  - **Mode A (Specific Value)**: Filters elements where a specific parameter contains a defined text/value (case-insensitive).
  - **Mode B (Is Not Empty)**: Filters elements simply by checking if a specific parameter has *any* value assigned (skips blank parameters).
- **Safe Execution**: Built-in protections against `NoneType` errors, unplaced elements, and read-only parameters.
- **User-Friendly UI**: Integrates with the `Data-Shapes` package to provide a clean pop-up window for selecting the Scope Box inside Revit or Dynamo Player.

## 🛠️ How It Works (Dynamo Logic)

The script processes data through a 5-input Python node:
1. **Scope Box**: The spatial boundary constraint.
2. **Elements**: Input list of elements/categories to check (e.g., Ducts, Pipes, Electrical Equipment).
3. **Target Parameter**: Name of the parameter where the new value will be written.
4. **New Value**: The value to be written.
5. **Filter Parameter**: Name of the parameter used to filter the input elements.
6. **Filter Value**: *(Optional)* The specific value to look for. If left empty, the script automatically switches to "Check if Filled" mode.

## 📋 Prerequisites

- **Autodesk Revit** (2022 or newer recommended)
- **Dynamo BIM**
- **Data-Shapes** Dynamo Package (for the UI Dropdown Selection)

## 💻 Python Code Snippet (Revit API)

The core logic uses a highly optimized Revit API approach (`Autodesk.Revit.DB.Outline` and `Outline.Contains`) which avoids heavy Dynamo geometry overhead and executes in seconds.

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.
