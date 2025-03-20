#!/bin/bash

echo "Welcome to the File Permission Manager!"

# Prompt for a directory name
read -p "Enter the name of a directory to create: " directory_name
mkdir -p $directory_name
cd $directory_name

echo "Directory '$directory_name' created and opened."

# Prompt for file creation
read -p "Enter the number of files you want to create: " file_count

for ((i=1; i<=file_count; i++))
do
    read -p "Enter the name for file $i: " file_name
    touch $file_name
    echo "File '$file_name' created."
done

echo "All files created! Here's the list:"
ls -l

# Set permissions for each file
for ((i=1; i<=file_count; i++))
do
    read -p "Enter the name of the file to set permissions: " file_name
    read -p "Enter the permissions (e.g., 644, 755): " permissions
    chmod $permissions $file_name
    echo "Permissions for '$file_name' set to $permissions."
done

# Display updated permissions
echo "Updated permissions:"
ls -l

# Special permissions
read -p "Do you want to create a shared directory with special permissions? (y/n): " response
if [[ $response == "y" ]]; then
    read -p "Enter the name of the shared directory: " shared_dir_name
    mkdir $shared_dir_name
    chmod +t $shared_dir_name
    chmod g+s $shared_dir_name
    echo "Shared directory '$shared_dir_name' created with sticky bit and setgid."
    ls -ld $shared_dir_name
fi

echo "Permission Manager script complete!"
