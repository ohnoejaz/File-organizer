Here's a breakdown of the code:

1: Import Libraries:
os: Provides functions to interact with the operating system.
shutil: Offers a way to move files and directories.

2: Set Directory:
directory = os.path.join(os.path.expanduser("~"), "Documents")
This line constructs the path to the "Documents" folder in the user's home directory.

3: Define Extensions:
A dictionary named extensions maps file extensions (like .jpg, .mp4) to folder categories (like "Image", "Videos").

4: Iterate Through Files:
for filename in os.listdir(directory):
Loops over each item in the specified directory.

5: Check File Type:
if os.path.isfile(file_path):
Ensures that the item is a file, not a directory.

6: Extract and Match Extension:
extension = os.path.splitext(filename)[1].lower()
Extracts the file extension and converts it to lowercase.
Checks if the extension is in the extensions dictionary.

7: Create Destination Folder:
folder_name = extensions[extension]
Finds the corresponding folder name for the extension.
os.makedirs(folder_path, exist_ok=True)
Creates the folder if it doesn't already exist.

8: Move File:
shutil.move(file_path, destination_path)
Moves the file to the appropriate folder.

9: Logging:
Prints a message stating whether the file was moved or skipped.

10: Completion Message:
print("File organization completed.")
Indicates that the script has finished running.
This script organizes files in your "Documents" folder into categorized subfolders based on their extensions.