# File-handling-and-exception-handling-assignment-
def read_and_modify_file():
    # creating filename
    input_filename = input("Please enter the filename to read: ")
    
    try:
        # opening and reading the file
        with open(input_filename, 'r') as file:
            content = file.read()  # Read the entire content
        
        # Modifying the content (e.g., converting lowercase to uppercase)
        modified_content = content.upper()

        # Creating new filename for the modified content
        output_filename = 'modified_' + input_filename
        
        # Writing the modified version to a new file
        with open(output_filename, 'w') as file:
            file.write(modified_content)

        print(f"Success! The modified content has been written to '{output_filename}'.")

    except FileNotFoundError:
        print("Error: The file does not exist.")
    except IOError:
        print("Error: The file could not be read.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Running the file read and write function
read_and_modify_file()
