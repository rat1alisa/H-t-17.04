# H-t-17.04

#include <iostream>
#include <string>
#include <algorithm>
#include <vector>
#include <iomanip>
#include <cmath>
using namespace std;

class Reservoir
{
public:
    char* name = new char[50];
    double lenth;
    double width;
    double depth;
    
    //----------
    char* get_name() { return name; };    
    double get_lenth() { return lenth; };
    double get_width() { return width; };
    double get_depth() { return depth; };

    char* set_nme() { return name; };    
    double set_lenth() { return lenth; };
    double set_width() { return width; };
    double set_depth() { return depth; };
    //---------
    
    Reservoir() {};
    
    explicit Reservoir(char* name, double lenth, double width, double depth) 
    {
        this->name = name;
        this->lenth = lenth;
        this->width = width;
        this->depth = depth;
    };
    
    Reservoir(const Reservoir &re)
    {
        name = re.name;
        lenth = re.lenth;
        width = re.width;
        depth = re.depth;
    }
    
    ~Reservoir() {};
    
    void New()
    {
        cout << "Enter information about the new reservoir: \n";
        cin >> width;
        cout << endl;
        cin >> lenth;
        cout << endl;
        cin >> depth;
    };
    
    void Input()
    {
    		cout << "Enter the data: " << endl;
    		cout << "Reservoir name - ";
    		cin >> name;
    		cout << "Length - ";
    		cin >> lenth;
    		cout << "Width - ";
    		cin >> width;
    		cout << "Depth - ";
    		cin >> depth;
    		cout << endl;
    };
    
    void Print()
    {
        cout << "Reservoir Name: " << name << endl;
        cout << "Width : " << width << endl;
        cout << "Length :" << lenth << endl;
        cout << "Depth : " << depth << endl;
        cout << endl;
    };
    
    void Volume()
    {
        int Vlm = width * lenth * depth;
        cout << "Reservoir volume - " << Vlm << endl;
        cout << endl;
    };
    
    void Area()
    {
        int Ar = width * lenth;
        cout << "Reservoir area - " << Ar << endl;
        cout << endl;
    };
    
    void SizeCheck()
    {
        if (lenth*width*depth < 3000)
        {
            cout << name << " - This is pool." << endl;
        }
        else
        {
            cout << name << " - This is sea." << endl;
        }
    }
};

int main()
{
    int n = 3;
    Reservoir* r1 = new Reservoir[n];
    Reservoir r2;
    int ch;
    cout << endl;
    cout << " 1 - Enter information.\n";
    cout << " 2 - Output information. \n";
    cout << " 3 - Volume.\n";
    cout << " 4 - Area.\n";
    cout << " 5 - Add new.\n";
    cout << " 6 - Check.\n";
    cout << " 7 - Other.\n";
    do {
        cout << "Select the required operation - ";
        cin >> ch;
        switch (ch)
        {
            case 1: (ch == 1);
            {
                r2.Input();
                break;
            }
            case 2: (ch == 2);
            {
                r2.Print();
                break;
            }
            case 3: (ch == 3);
            {
                r2.Volume();
                break;
            }
            case 4: (ch == 4);
            {
                r2.Area();
                break;
            }
            case 5: (ch == 5);
            {
                r2.New();
                r2.Print();
                break;
            }
            case 6: (ch == 6);
            {
                r2.SizeCheck();
                break;
            }
            case 7: (ch == 7);
            {
                cout << "Unfortunately, you are only provided with suggested operations.\n";
                break;
            }
            default:
            {
                cout << "ERROR!\n";
                break;
            }
        }
    } 
    while (ch != 7);
{
}
}

