# Emergency Room Triage System

A Java-based application that implements a priority queue system for managing emergency room patients based on their conditions and ages. This system helps medical facilities efficiently organize and process patients according to the severity of their conditions or other criteria.

## Project Overview

The Emergency Room Triage System uses a heap-based priority queue to manage patients entering an emergency room. It can prioritize patients based on either:
- Medical condition severity (Critical > Severe > Mild > Light)
- Patient age

## Features

- Priority queue implementation using a heap data structure
- Flexible patient prioritization:
  - Condition-based prioritization (default)
  - Age-based prioritization (optional)
- Support for both small and large datasets
- Patient information management including:
  - First name
  - Last name
  - Age
  - Medical condition

## Project Structure

```
.
├── lib/                  # Library dependencies
├── src/
│   ├── app/             # Main application code
│   │   ├── AppMain.java             # Entry point
│   │   ├── Condition.java           # Patient condition enum
│   │   ├── Patient.java            # Patient data model
│   │   ├── PatientAgeComparator.java       # Age-based sorting
│   │   ├── PatientConditionComparator.java  # Condition-based sorting
│   │   └── TriageSystemParser.java  # Input file parser
│   ├── priorityqueue/   # Priority queue implementation
│   └── test/           # Test files
├── large_input.txt     # Large dataset for testing
└── small_input.txt     # Small dataset for testing

## Usage

1. The system reads patient data from either `small_input.txt` or `large_input.txt`
2. Patients are automatically sorted based on the chosen prioritization method
3. The system processes patients in order of priority

## Input File Format

The input files should contain patient information in the following format:
```
FirstName LastName Age Condition
```
Where:
- FirstName and LastName are strings
- Age is an integer
- Condition is one of: LIGHT, MILD, SEVERE, or CRITICAL

## Customization

The system can be customized to prioritize patients based on:
- Medical condition (using `PatientConditionComparator`)
- Age (using `PatientAgeComparator`)

To switch between prioritization methods, modify the comparator initialization in `AppMain.java`.

## Implementation Details

The system uses a binary heap implementation for the priority queue, which provides:
- O(log n) time complexity for enqueue and dequeue operations
- O(1) time complexity for peek operations
- Efficient memory usage

## Getting Started

1. Clone the repository
2. Ensure you have Java installed
3. Compile the project
4. Run `AppMain.java`
5. The system will process and display patients in priority order 