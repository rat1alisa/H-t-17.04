# H-t-17.04


#include <iostream>
#include <string>
using namespace std;

class Reservoir
{
public:
    string name;
    int length;
    int width;
    int depth;
    
    //Reservoir() {};
    Reservoir(string p_name, int p_length, int p_width, int p_depth)
    {
        name = p_name;
        length = p_length;
        width = p_width;
        depth = p_depth;
    }

    void Input()
    {
    		cout << "Enter the data: " << endl;
    		cout << "Reservoir name - ";
    		cin >> name;
    		cout << "Length - ";
    		cin >> length;
    		cout << "Width - ";
    		cin >> width;
    		cout << "Depth - ";
    		cin >> depth;
    }   
    void Print()
    {
        cout << "Reservoir Name: " << name << endl;
        cout << "Width : " << width << endl;
        cout << "Length :" << length << endl;
        cout << "Depth : " << depth << endl;
    }
    void Volume()
    {
        cout << "Reservoir volume - " << width*length*depth << endl;
    }
    void Area()
    {
        cout << "Reservoir area - " << width*length << endl;
    }
    void SizeCheck()
    {
        if (length*width*depth < 3000)
        {
            cout << name << " - This is pool." << endl;
        }
        else
        {
            cout << name << " - This is sea." << endl;
        }
    }
    Reservoir(const Reservoir &re)
    {
        name = re.name;
        length = re.length;
        width = re.width;
        depth = re.depth;
    }
};

int main()
{
    int n = 50;
    Reservoir first;
    first.Input();
    first.Print();
    first.Volume();
    first.Area();
    first.SizeCheck();
    Reservoir second = first;
}
