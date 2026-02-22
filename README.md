#include <iostream>
#include <vector>
#include <string>

struct Student {
    int index;
    std::string name;
    void display() {
        std::cout << "Index: " << index << ", Name: " << name << "\n";
    }
};

std::vector<Student> students;

void addStudent() {
    int idx;
    std::string name;
    std::cout << "Enter Index Number: ";
    std::cin >> idx;
    std::cout << "Enter Name: ";
    std::cin.ignore();
    std::getline(std::cin, name);
    students.emplace_back(Student{idx, name});
}

void viewStudents() {
    for (auto& s : students) {
        s.display();
    }
}
