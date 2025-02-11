# CodeAlpha-Task-Number-2
#include <iostream>
#include <fstream>
#include <string>
#include <cstdio> // For remove()
#include <windows.h> // Windows-specific functions
#include <direct.h> // For directory handling (optional)

using namespace std;

void createFile(const string& filename) {
    ofstream file(filename);

    if (file) { // Check if file is successfully opened
        cout << "File '" << filename << "' created successfully.\n";
        file.close();
    } else {
        cerr << "Error creating file '" << filename << "'. Check permissions or path.\n";
    }
}

void deleteFile(const string& filename) {
    if (remove(filename.c_str()) == 0) {
        cout << "File '" << filename << "' deleted successfully.\n";
    } else {
        perror("Error deleting file"); // Prints the error message
    }
}

int main() {
    string filename = "testfile.txt";

    createFile(filename);
    
    // Pause to check if file is created
    cout << "Check if the file is created, then press Enter...\n";
    cin.get(); 

    deleteFile(filename);
    
    return 0;
}
