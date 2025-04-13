# PLP-Python-assignment-week-4
def process_file():
    """Reads a file, modifies content, and writes to a new file with error handling."""
    try:
        # Get filename from user
        input_filename = input("Enter the filename to read: ")
        output_filename = input("Enter the filename to save modified content: ")

        # Read original file
        with open(input_filename, 'r') as input_file:
            content = input_file.read()

        # Modify content (example: convert to uppercase)
        modified_content = content.upper()

        # Write to new file
        with open(output_filename, 'w') as output_file:
            output_file.write(modified_content)

        print(f"Success! Modified content saved to {output_filename}")

    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
    except PermissionError:
        print(f"Error: You don't have permission to read/write files.")
    except IsADirectoryError:
        print(f"Error: '{input_filename}' is a directory, not a file.")
    except UnicodeDecodeError:
        print("Error: Could not decode the file (try a different encoding).")
    except Exception as e:
        print(f"An unexpected error occurred: {str(e)}")
    finally:
        print("File processing complete.")

# Run the program
if __name__ == "__main__":
    process_file()
