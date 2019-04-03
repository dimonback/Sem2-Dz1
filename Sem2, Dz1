#include <cstdio>
#include <cstdlib>
#include <iostream>
#include <math.h>

using namespace std;

class Triangle;
class Dot
{
    friend class Triangle;
    friend istream& operator>>(istream&, Dot&);
private:
    float x;
    float y;
public:
    Dot(float xx=0.0, float yy=0.0) : x(xx), y(yy) { };
    Dot centre(Dot&);
    float getx() { return x; };
    float gety() { return y; };
};

class Triangle
{
private:
    Dot p1;
    Dot p2;
    Dot p3;
public:
    Triangle(Dot& p, Dot& q, Dot& v) : p1(p), p2(q), p3(v) {};
    float square();
};

Dot Dot::centre(Dot& m)
{
    float dx = ((this->x + m.x)/2);
    float dy = ((this->y + m.y)/2);
    return Dot(dx,dy);
}

float Triangle::square()
{
    float a,b,c,p,Sq;
    a = sqrt((this->p1.x-this->p2.x)*(this->p1.x-this->p2.x) + (this->p1.y-this->p2.y)*(this->p1.y-this->p2.y));
    b = sqrt((this->p2.x-this->p3.x)*(this->p2.x-this->p3.x) + (this->p2.y-this->p3.y)*(this->p2.y-this->p3.y));
    c = sqrt((this->p3.x-this->p1.x)*(this->p3.x-this->p1.x) + (this->p3.y-this->p1.y)*(this->p3.y-this->p1.y));
    p = (a+b+c)/2;
    Sq = sqrt(p*(p-a)*(p-b)*(p-c));
    return Sq;
}

istream& operator >>(istream& input, Dot& p)
{
    char semicolon = ';';
    input >> p.x >> semicolon >> p.y;
    return input;
}

int main(){
    Dot A,B,C, Q,W,E;
    float xa,ya,xb,yb,xc,yc, S;
    cout << "Enter 3 dot coordinates"<<endl;
    cin >> A >> B >>C;
    ya = A.gety();
    yb = B.gety();
    yc = C.gety();
    xa = A.getx();
    xb = B.getx();
    xc = C.getx();
    
   Q = A.centre(B);
   W = B.centre(C);
   E = C.centre(A);
   Triangle G(Q,W,E);
    S = G.square();
    cout << S;
}

