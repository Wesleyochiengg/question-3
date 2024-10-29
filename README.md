#include <iostream>
#include <string>
#include <cmath>

using namespace std;

class Shape {
protected:
    string color;

public:
    Shape(string c) : color(c) {}
    string getColor() {
        return color;
    }
};

class Rectangle : public Shape {
private:
    float length;
    float width;

public:
    Rectangle(float l, float w, string c) : Shape(c), length(l), width(w) {}
    float area() {
        return length * width;
    }
};

class Circle : public Shape {
private:
    float radius;

public:
    Circle(float r, string c) : Shape(c), radius(r) {}
    float area() {
        return M_PI * radius * radius;
    }
};

int main() {
    Rectangle rect(15, 10, "blue");
    Circle circ(2, "pink");

    cout << "Rectangle Color: " << rect.getColor() << ", Area: " << rect.area() << endl;
    cout << "Circle Color: " << circ.getColor() << ", Area: " << circ.area() << endl;

    return 0;
}
