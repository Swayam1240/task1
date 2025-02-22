# task1
#include <iostream>
#include <fstream>

using namespace std ;

class filemanager{
    public :
        string filename ;
    {
        filemanager(string file)
        filename = file ;
    }
};

void readfile(const string &filename){
    ifstream file(filename) ;
    if(!file){
        cout<<"file does not exist" ;
        return ;
    }
    string line ;
    while(getline(file , line)){
        cout<<line<<endl;
    }
    file.close();
}

void writefile(const string &filename){
    ofstream file(filename , ios::app) ;

    if(!file){
        cout<<"unable to open file" << endl ;
    }
    string data ;
    while(getline(cin , data)){
        file<<data<<endl;
    cout<<"data save successfully"<<endl;
    }
    file.close() ;
}

int main(){
    filemanager file("task1.txt") ;
    int choice ;
    do{
        cout<<"1. write to file \n 2. read to file" << endl ;
        cin>>choice;
    
        switch (choice)
        {
        case 1 :
            file.writefile();
            break;
        case 2 : 
            file.readfile();
            break; 
        default:
            cout<<"invalid choice"<<endl;
            break;
        }
    }
    while(choice != 3){
        cout << "invalid choice" << endl ;
    }
    
}


