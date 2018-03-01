// Frame

#include<iostream>
using namespace std;


void main()
{
	//Deklarationsteil
	//two Arrays that represent one generation
	//automatonLine[] for checking and automatonNewLine[] for generating a new generation

	int automatonLine[101] = { 0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0 };
	int automatonNewLine[101] = { 0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0 };
	int ngen;
	int rnum;
	int rbin;
	int j = 0;
	int rulea = 0;	//{0,0,0} (1)
	int ruleb = 0;	//{0,0,1} (2)
	int rulec = 0;	//{0,1,0} (4)
	int ruled = 0;	//{0,1,1} (8)
	int rulee = 0;	//{1,0,0} (16)
	int rulef = 0;	//{1,0,1} (32)
	int ruleg = 0;	//{1,1,0} (64)
	int ruleh = 0;	//{1,1,1} (128)
	
	cout << "-----------------------------" << endl;
	cout << "-----Wolfram Automaton!!-----" << endl;
	cout << "-----------------------------" << endl << endl;

	cout << "Which rule? (from 0 to 255)" << endl;
	cin >> rnum;
	cout << endl;

	while (rnum > 0)

	{

		rbin = rnum % 2;

		if (j == 0) 
		{
			rulea = rbin;
		}
		else if (j == 1) 
		{
			ruleb = rbin;
		}
		else if (j == 2) 
		{
			rulec = rbin;
		}
		else if (j == 3)
		{
			ruled = rbin;
		}
		else if (j == 4)
		{
			rulee = rbin;
		}
		else if (j == 5)
		{
			rulef = rbin;
		}
		else if (j == 6)
		{
			ruleg = rbin;
		}
		else if (j == 7)
		{
			ruleh = rbin;
		}

		rnum /= 2;

		j++;

	}

	cout << "Number of generations: ";
	cin >> ngen;
	cout << endl;


	/*
	most interesting rulesets:
	00011110 (rule 30)
	01111110 (rule 126)
	00110110 (rule 54)
	10010110 (rule 150)
	00111100 (rule 60)
	10011110 (rule 158)
	00111110 (rule 62)
	10110110 (rule 182)
	01011010 (rule 90)
	10111100 (rule 188)
	01011110 (rule 94)
	10111110 (rule 190)
	01101110 (rule 102)
	11011100 (rule 220)
	01101110 (rule 110)
	11011110 (rule 222)
	01111010 (rule 122)
	11111010 (rule 250)
	*/

	for (int i = 0; i < 101; i++)
	{
		if (automatonLine[i] == 1)
		{
			cout << (char)219;
		}
		else
		{
			cout << " ";
		}
	}
	cout << endl;
	//Check rules
	/*
	{0,0,0} = rulea
	{0,0,1} = ruleb
	{0,1,0} = rulec
	{0,1,1} = ruled
	{1,0,0} = rulee
	{1,0,1} = rulef
	{1,1,0} = ruleg
	{1,1,1} = ruleh

	For checking:
	checking automatonLine[i]
	{i-1, i, i+1} = automatonNewLine[i]
	bei i = 51 dann soll automatonLine[0] gecheckt werden
	*/
	for (int n = 0; n < ngen; n++)
	{
		for (int i = 0; i < 101; i++)
		{
			if (i == 0) 
			{
				if (automatonLine[100] == 0 && automatonLine[i] == 0 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = rulea;
				}
				else if (automatonLine[100] == 0 && automatonLine[i] == 0 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = ruleb;
				}
				else if (automatonLine[100] == 0 && automatonLine[i] == 1 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = rulec;
				}
				else if (automatonLine[100] == 0 && automatonLine[i] == 1 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = ruled;
				}
				else if (automatonLine[100] == 1 && automatonLine[i] == 0 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = rulee;
				}
				else if (automatonLine[100] == 1 && automatonLine[i] == 0 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = rulef;
				}
				else if (automatonLine[100] == 1 && automatonLine[i] == 1 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = ruleg;
				}
				else if (automatonLine[100] == 1 && automatonLine[i] == 1 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = ruleh;
				}
			}
			else if (i == 100) 
			{
				if (automatonLine[i - 1] == 0 && automatonLine[i] == 0 && automatonLine[0] == 0)
				{
					automatonNewLine[i] = rulea;
				}
				else if (automatonLine[i - 1] == 0 && automatonLine[i] == 0 && automatonLine[0] == 1)
				{
					automatonNewLine[i] = ruleb;
				}
				else if (automatonLine[i - 1] == 0 && automatonLine[i] == 1 && automatonLine[0] == 0)
				{
					automatonNewLine[i] = rulec;
				}
				else if (automatonLine[i - 1] == 0 && automatonLine[i] == 1 && automatonLine[0] == 1)
				{
					automatonNewLine[i] = ruled;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 0 && automatonLine[0] == 0)
				{
					automatonNewLine[i] = rulee;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 0 && automatonLine[0] == 1)
				{
					automatonNewLine[i] = rulef;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 1 && automatonLine[0] == 0)
				{
					automatonNewLine[i] = ruleg;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 1 && automatonLine[0] == 1)
				{
					automatonNewLine[i] = ruleh;
				}
			}
			else {
				if (automatonLine[i - 1] == 0 && automatonLine[i] == 0 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = rulea;
				}
				else if (automatonLine[i - 1] == 0 && automatonLine[i] == 0 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = ruleb;
				}
				else if (automatonLine[i - 1] == 0 && automatonLine[i] == 1 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = rulec;
				}
				else if (automatonLine[i - 1] == 0 && automatonLine[i] == 1 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = ruled;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 0 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = rulee;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 0 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = rulef;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 1 && automatonLine[i + 1] == 0)
				{
					automatonNewLine[i] = ruleg;
				}
				else if (automatonLine[i - 1] == 1 && automatonLine[i] == 1 && automatonLine[i + 1] == 1)
				{
					automatonNewLine[i] = ruleh;
				}
			}
		}


	//NewLine to Line
	//The New Generation becomes standard
	//automatonLine[i] = automatonNewLine[i] in a for loop
	for (int i = 0; i < 101; i++)
	{
		automatonLine[i] = automatonNewLine[i];
	}

	//cout Line
	for (int i = 0; i < 101; i++)
	{
		if (automatonLine[i] == 1)
		{
			cout << (char)219;
		}
		else
		{
			cout << " ";
		}
	}
	cout << endl;
}

	cout << endl << "BOOOM!" << endl << endl;



	system("pause");
}
