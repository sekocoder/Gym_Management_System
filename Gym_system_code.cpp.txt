#include<iostream>
#include<conio.h>
#include<string.h>
#include<string>
#include<cstring>

using namespace std;

class declaration
{   public:
	string id, name, age, address, contact, designation, experience;
	string status;
	declaration ()
	{ status = "Not Paid" ; }
};


class count
{   public:
	int counter;
	count () 
      {counter = 0 ;}
};


class member : public count, public declaration
{   public:
	declaration m[50];
	int mn;
	string back;
	int memberid, status1, status2, fee, memberfee;
	
	member () 
	{ fee=0; memberid=0; status1=0; status2=0; memberfee=0; }

	void get_data()
	{   cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\tHow many members do you want to add: ";
		cin >> mn;
		system("cls");
		for(int i = 0; i < mn; i++)
		{	cout << "\n\n\t\t\t\t\t\t\t\tAlot unique ID to member " << i + 1 << ": ";
			cin.ignore();
			getline(cin, m[memberid].id);
			cout << "\n\n\t\t\t\t\t\t\t\tName                      : ";
			getline(cin, m[memberid].name);
			cout << "\n\n\t\t\t\t\t\t\t\tAge                       : ";
			getline(cin, m[memberid].age);
			cout << "\n\n\t\t\t\t\t\t\t\tAddress                   : ";
			getline(cin, m[memberid].address);
			cout << "\n\n\t\t\t\t\t\t\t\tContact                   : ";
			getline(cin, m[memberid].contact);
			memberid++;
			counter++;
			back:
			cout << endl << endl;
			cout << "\t\t\t\t\t\t\t\tProceed Forward[Y/N]      : ";
			cin >> back;
			if(back == "Y" || back == "y")
			{ 	cout << "\n\n\t\t\t\t\t\t\t\tYou filled all Entries of " << i + 1 << "/" << mn << " member successfully...";
				getch();
				cout << endl;
			}
			else if(back =="N" || back == "n")
				break;

			else
			{   cout << "\n\t\t\t\t\t\t\t\tWrong Input";
				goto back;
			}
		}
	}
		
	void show_data()
	{   system("cls");
        string n;
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tEnter the member's ID  to display Record: ";
    	cin >> n;
    	system("cls");
        if(n == "0")
        {   system("cls");
            cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tOOPS!!!!"<< endl;
            cout << "\t\t\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
        }
    	else
    	{   int i;
        	for(i = 0; i < memberid; i++)
        	{
        		status1 = 0;
        	    if(n == m[i].id)
        	    {   status1 = 1; 
        	        break;
        	    }    
        	}
        	
        		if(status1) 
            	{   cout << "\n\n\n\n\n\n\n\n\n\n";
        		    cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
        		    cout << "\t\t\t\t\t\t\t\tMembers's ID                 :" << m[i].id << endl << endl;
        	    	cout << "\t\t\t\t\t\t\t\tMembers's Name               :" << m[i].name << endl << endl;
        	    	cout << "\t\t\t\t\t\t\t\tMember's Age                 :" << m[i].age << endl << endl;
        	    	cout << "\t\t\t\t\t\t\t\tMember's Address             :" << m[i].address << endl << endl;
        	    	cout << "\t\t\t\t\t\t\t\tMembers's Contact            :" << m[i].contact << endl << endl;
        	    	cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
        	    	cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
        		}
            	else
   		    	{   cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\tNo such ID in database" << endl;
        	    	cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
            	}
        }
        getch();
	}
		
	void all_members_data()
   	{ 	if(memberid == 0)
      	{	system("cls");
      		cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!\n";
      		cout << "\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
    	}
	 	else
		{   cout << "\n\n\n\n\n\n\n\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
    		cout << "\t\t\t\t\t\t\t\t\t  Details Of All The Members In The GYM" << endl << endl;
    	    cout << "\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
            cout << "\t\t\t\t\t\tID" << "\t\t\t" << "NAME" << "\t\t\t" << "AGE" << "\t\t\t" << "Contact\n\n";
       	
       		for(int i = 0; i < memberid; i++)
       		 cout << "\t\t\t\t\t\t" << m[i].id << "\t\t\t" << m[i].name << "\t\t\t" << m[i].age << "\t\t\t" << m[i].contact << endl << endl;
        		
        	cout << "\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
       		cout<<"\n\t\t\t\t\t\tPress any key to choose another option...";
       	}
        getch();
    }
    	

   	void total_members()
    {   system("cls");
        int i = counter;
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t-----------------------------------------" << endl << endl;
        cout << "\t\t\t\t\t\t\t\tTotal Members in GYM: " << i <<"\n\n\t\t\t\t\t\t\t\t-----------------------------------------\n\n";
        cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
        getch();
    }


    void record_fee()
    {   system("cls");
        string n;
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tEnter the member's ID  to Record Fee> ";
    	cin >> n;
        if(n == "0")
        {   system("cls");
            cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!"<< endl;
            cout << "\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
        }
    	else
    	{   int i;
        	for(i = 0; i < memberid; i++)
        	{   status2 = 0;
        	    if(n == m[i].id)
        	    {   status2 = 1; 
        	        break;
        	    }    
        	}
        	
        		if(status2) 
            	{   fee++;
        	    	memberfee += 500;
        	    	m[i].status = "    Paid";
        	    	system("cls");
        		    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\t\tFee Paid...";
        		}
            	else
   		    	{   system("cls");
        		    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tNo such ID in database " << endl;
        	    	cout << "\t\t\t\t\t\t\tPress any key to choose another option...";
            	}
        }
        getch();
	}

	void show_fee()
	{  	if(memberid == 0)
      	{   system("cls");
      		cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!" << endl;
      		cout << "\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
    	}
	 	else
		{   system("cls");
    		cout << "\n\n\n\n\n\n\n\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
    		cout << "\t\t\t\t\t\t\t\t\tFee Record Of All The Members In The GYM" << endl << endl;
    	    cout << "\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\tTotal Members: " << counter <<"\n\n\t\t\t\t\t\tMembers that paid fee: " << fee << endl << endl;
			cout << "\t\t\t\t\t\tID" << "\t\t\t" << "NAME" << "\t\t\t" << "Contact" << "\t\t\t" << "Status\n\n";

       		for(int i = 0; i < memberid; i++)
        	 cout << "\t\t\t\t\t\t" << m[i].id << "\t\t\t" << m[i].name << "\t\t\t" << m[i].contact << "\t\t" << m[i].status << endl;

        	cout << "\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
       		cout<<"\n\t\t\t\t\t\tPress any key to choose another option...";
       	}
        getch();
	}    
};


class employee : public count , public declaration
{   public:
	declaration e[50];
	int i, en;
	string back;
	int pay, employeeid, status3, status4, emp_pay_given;
	
	employee ()
		{ pay = 0; employeeid = 0; status3 = 0; status4 = 0; emp_pay_given = 0 ; } 
	
	void get_data()
	{   cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tHow many employees do you want to add: ";
		cin >> en;
		system("cls");
		for(i = 0; i < en; i++)
		{	cout << "\n\n\t\t\t\t\t\t\t\tAlot unique ID to employee " << i + 1 << ": ";
			cin.ignore();
			getline(cin, e[employeeid].id);
			cout << "\n\n\t\t\t\t\t\t\t\tName                       : ";
			getline(cin, e[employeeid].name);
			cout << "\n\n\t\t\t\t\t\t\t\tAge                        : ";
			getline(cin, e[employeeid].age);
		    cout << "\n\n\t\t\t\t\t\t\t\tDesignation                : ";
			getline(cin, e[employeeid].designation);
			cout << "\n\n\t\t\t\t\t\t\t\tExperience                 : ";
			getline(cin, e[employeeid].experience);
			employeeid++;
			counter++;
			cout << endl << endl;
			back1:
			cout << "\t\t\t\t\t\t\t\tProceed Forward[Y/N]       : ";
			cin >> back;

			if(back == "Y" || back == "y")
			{	cout << "\n\n\t\t\t\t\t\t\t\tYou filled all Entries of " << i + 1 << "/" << en << " employee successfully...";
				getch();
				cout << endl;
			}
			else if(back =="N" || back == "n")
			    break;
			else
			{   cout << "\n\t\t\t\t\t\t\t\tWrong Input" << endl;
				goto back1;
			}
		}
	}
		
	void show_data()
	{   system("cls");
		int i;string n;
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tEnter the employee's ID  to display Record: ";
    	cin >> n;
    	system("cls");
        if(n == "0")
        {   system("cls");
            cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tOOPS!!!!"<< endl;
            cout << "\t\t\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
        }
        
    	else
    	{   
        	for(i = 0; i < employeeid; i++)
        	{   status3 = 0;
        	    if(n == e[i].id)
        	    {   status3 = 1;
        	        break;
        	    }   
        	}
        	if(status3) 
            {   cout << "\n\n\n\n\n\n\n\n\n\n";
        	    cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
        	    cout << "\t\t\t\t\t\t\t\t<1> Employee's ID                 :" << e[i].id << endl << endl;
        	    cout << "\t\t\t\t\t\t\t\t<2> Employee's Name               :" << e[i].name << endl << endl;
        	    cout << "\t\t\t\t\t\t\t\t<3> Employee's Age                :" << e[i].age << endl << endl;
        	    cout << "\t\t\t\t\t\t\t\t<4> Employee's Designation        :" << e[i].designation << endl << endl;
        	    cout << "\t\t\t\t\t\t\t\t<5> Employee's Experience         :" << e[i].experience << endl << endl;
        	    cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
        	    cout << "\n\t\t\t\t\t\t\t\tPress any key to choose another option...";
        	}
            else
   		    { cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\tNo such ID in database " << endl;
        	  cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
            }
        }
        getch();
	}
    	    		
	void all_employees_data()
   	{   int i;
      	if(employeeid == 0)
      	{   system("cls");
      		cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!" << endl;
      		cout << "\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
    	}
	 	else
		{   cout << "\n\n\n\n\n\n\n\t\t\t\t\t\t---------------------------------------------------------------------------------------" << endl << endl;
    		cout << "\t\t\t\t\t\t\t\t\tDetails Of All The Employees In The GYM" << endl << endl;
    	    cout << "\t\t\t\t\t\t---------------------------------------------------------------------------------------" << endl << endl;
    		cout << "\t\t\t\t\t\tID" << "\t\t\t" << "NAME" << "\t\t\t" << "AGE" << "\t\t\t" << "DESIGNATION\n\n";

       		for(i = 0; i < employeeid; i++)
       		 cout <<"\t\t\t\t\t\t" <<e[i].id <<"\t\t\t" <<e[i].name <<"\t\t\t" <<e[i].age <<"\t\t\t" <<e[i].designation <<endl <<endl;
        		
        	cout <<"\t\t\t\t\t\t---------------------------------------------------------------------------------------" <<endl <<endl;
       		cout <<"\t\t\t\t\t\tPress any key to choose another option...";
       	}
        getch();
    }
    	
    void total_employees()
    {   system("cls");
        int i = counter;
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t-----------------------------------------" << endl << endl;
        cout << "\t\t\t\t\t\t\t\tTotal Members in GYM: " << i << endl << endl;
        cout << "\t\t\t\t\t\t\t\t-----------------------------------------" << endl << endl;
        cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
        getch();
    }
    
    void record_pay()
    {   system("cls");
        string n;
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tEnter the employee's ID  to Record payment: ";
    	cin >> n;
        if(n == "0")
        {   cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!" << endl;
            cout << "\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
        }
    	else
    	{   int i;
        	for(i = 0; i < employeeid; i++)
        	{   status4 = 0;
        	    if(n == e[i].id)
        	    {   status4 = 1; 
        	        break;
        	    }    
        	}
        	
        		if(status4) 
            	{   pay++;
        	    	emp_pay_given += 500;
        	    	e[i].status = "Paid";
        		    system("cls");
        		    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\t\tPay Given...";
        		}
            	else
   		    	{   system("cls");
        		    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tNo such ID in database " << endl;
        	    	cout << "\t\t\t\t\t\t\tPress any key to choose another option...";
            	}
        }
        getch();
	}

	void show_pay()
	{ 	if(employeeid == 0)
      	{   system("cls");
      		cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!" << endl;
      		cout << "\t\t\t\t\t\t\tNote: No Record To Display  Plz Go Back And Enter Some Entries...";
    	}
	 	else
		{   system("cls");
			cout << "\n\n\n\n\n\n\n\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
    		cout << "\t\t\t\t\t\t\t\t\tPay Record Of All The Employees In The GYM" << endl << endl;
    	    cout << "\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\tTotal Employees: " << counter << endl << endl;
			cout << "\t\t\t\t\t\tEmployees that Received Pay:" << pay << endl << endl;
        	cout << "\t\t\t\t\t\tID" << "\t\t\t" << "NAME" << "\t\t\t" << "Designation" << "\t\t\t" << "Status\n\n";

       		for(int i = 0; i < employeeid; i++)
        		cout <<"\t\t\t\t\t\t" <<e[i].id <<"\t\t\t" <<e[i].name <<"\t\t\t" <<e[i].designation <<"\t\t\t" <<e[i].status <<endl;

        	cout << "\t\t\t\t\t\t--------------------------------------------------------------------------------" << endl << endl;
       		cout<<"\n\t\t\t\t\t\tPress any key to choose another option...";
       	}
        getch();
	}   
};


class schedule
{   private:
		string mon, tue, wed, thurs, satur, sun;
		int chk;
	public:
		schedule()
		{ chk=0; }

	void feedbackmenu()
	    {   cout << "\t\t\t\t\t\t\t\t---------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t<1> Chest Workout     \t<2> Dumble rows" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t<3> Abs workout       \t<4> Glutes/Squarts" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t<5> Weightlose workout\t<6> Leg workout" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t---------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\tEnter your choice: ";
		}	
	
	void wronginput()
	    {   	system("cls");
				cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
    			cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
				getch();
		}

	void get_schedule()
		{   chk++;
			monday:
			system("cls");
			cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\tFor Monday" << endl << endl;
            feedbackmenu();
			cin >>mon;
			if(mon == "1")
				mon = "Chest day";
	        else if(mon == "2")
				mon = "Dumble rows day";
            else if(mon == "3")
				mon = "Abs day";
		    else if(mon == "4")
				mon = "Glutes day";
	        else if(mon == "5")
				mon = "Weightlose day";
	        else if(mon == "6")
				mon = "Leg day";
		    else 
			{   wronginput();
				goto monday;
			}
			tuesday:
			system("cls");
			cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\tFor Tuesday" << endl << endl;
			feedbackmenu();
			cin >>tue;
			if(tue == "1")
				tue = "Chest day";
		    else if(tue == "2")
				tue = "Dumble rows day";
		    else if(tue == "3")
				tue = "Abs day";
	        else if(tue == "4")
				tue = "Glutes day";
		    else if(tue == "5")
				tue = "Weightlose day";
            else if(tue == "6")
				tue = "Leg day";
	        else 
			{   wronginput();
				goto tuesday;
			}
			wednesday:
			system("cls");
			cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\tFor Wednesday" << endl << endl;
	        feedbackmenu();
			cin >>wed;
			if(wed == "1")
				wed = "Chest day";
            else if(wed == "2")
				wed = "Dumble rows day";
            else if(wed == "3")
				wed = "Abs day";
            else if(wed == "4")
				wed = "Glutes day";
            else if(wed == "5")
				wed = "Weightlose day";
	        else if(wed == "6")
				wed = "Leg day";
			else 
			{   wronginput();
				goto wednesday;
			}
			thursday:
			system("cls");
			cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\tFor Thursday" << endl << endl;
		    feedbackmenu();
			cin >>thurs;
			if(thurs == "1")
				thurs = "Chest day";
	        else if(thurs == "2")
				thurs = "Dumble rows day";
            else if(thurs == "3")
				thurs = "Abs day";
            else if(thurs == "4")
				thurs = "Glutes day";
            else if(thurs == "5")
				thurs = "Weightlose day";
            else if(thurs == "6")
				thurs = "Leg day";
	        else 
			{   wronginput();
				goto thursday;
			}
			saturday:
			system("cls");
			cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\tFriday is off\n\t\t\t\t\t\t\t\t----------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\tFor Saturday" << endl << endl;
		    feedbackmenu();
			cin >>satur;
			if(satur == "1")
				satur = "Chest day";
            else if(satur == "2")
				satur = "Dumble rows day";
            else if(satur == "3")
				satur = "Abs day";
	        else if(tue == "4")
				satur = "Glutes day";
            else if(satur == "5")
				satur = "Weightlose day";
            else if(satur == "6")
				satur = "Leg day";
			else 
			{   wronginput();
				goto saturday;
			}
			sunday:
			system("cls");
			cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\tFor Sunday" << endl << endl;
            feedbackmenu();
			cin >>sun;
			if(sun == "1")
				sun = "Chest day";
			else if(sun == "2")
				sun = "Dumble rows day";
			else if(sun == "3")
				sun = "Abs day";
			else if(sun == "4")
             	sun = "Glutes day";
	    	else if(sun == "5")
				sun = "Weightlose day";
			else if(sun == "6")
				sun = "Leg day";
        	else 
			{   wronginput();
				goto sunday;
			}
			system("cls");
			cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\tSchedule has been Resetted...";
			getch();
		}

	void show_schedule()
	{   if(chk == 0)
		{   system("cls");
			cout << "\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t\t\tNo record to show" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
			getch();
		}
		else
		{   system("cls");
			cout << "\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\t\tGYM Schedule" << endl << endl;
			cout << "\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\tMonday           :" << mon << endl << endl;
			cout << "\t\t\t\t\t\t\t\tTuesday          :" << tue << endl << endl;
			cout << "\t\t\t\t\t\t\t\tWednesday        :" << wed << endl << endl;
			cout << "\t\t\t\t\t\t\t\tThursday         :" << thurs << endl << endl;
			cout << "\t\t\t\t\t\t\t\tFriday is Off" << endl << endl;
			cout << "\t\t\t\t\t\t\t\tSaturday         :" << satur << endl << endl;
			cout << "\t\t\t\t\t\t\t\tSunday           :" << sun << endl << endl;
			cout << "\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
			cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
			getch();	
		}
	}
};


void login()
{   int pass;
	cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tGYM MANAGEMENT SYSTEM\n";
	cout << "\t\t\t\t\t\t\t\t\t------------------------------\n\n\t\t\t\t\t\t\t\t\tLOGIN\n";
	cout << "\t\t\t\t\t\t\t\t\t------------------------------\n\n\t\t\t\t\t\t\t\t\tEnter Password: ";

	cin>>pass;
	if(pass==123)
	{   system("cls");
    	cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\t  Access Granted!  ";
   		system ("cls");
   	}
	else
	{   system("cls");
    	cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tAccess Aborted" << endl;
		cout << "\t\t\t\t\t\t\t\t\tPlease Try Again\n\n\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
		getch(); 
		system("cls");
    	login();
	}
}


int main()
{   
	string ch1, ch2, ch3, ch4, ch5, ch6 ;
    member m1; employee e1; schedule s1;
    
system("cls");
cout << "\n\n\n\n\n\n\n\n\n";
cout << "\t\t\t\t\t _______________________________________________________________________________________ \n";
cout << "\t\t\t\t\t|                                           		                                |\n";
cout << "\t\t\t\t\t|                                           		                                |\n";
cout << "\t\t\t\t\t|                                                                                       |\n";
cout << "\t\t\t\t\t|                                       WELCOME TO                                      |\n";
cout << "\t\t\t\t\t|                                                                                       |\n";
cout << "\t\t\t\t\t|                                THE GYM MANAGEMENT SYSTEM                              |\n";
cout << "\t\t\t\t\t|                                                                                       |\n";
cout << "\t\t\t\t\t|                                                                                       |\n";
cout << "\t\t\t\t\t|   Made By - Siddharth Singh   Devanshu Patidar                                        |\n";
cout << "\t\t\t\t\t|              Mrinal Devnath   Sanket Santosh Diwate                                   |\n";
cout << "\t\t\t\t\t|_______________________________________________________________________________________|\n";
cout << "\n\n\n\n\t\t\t\t\t";
cout << "Press any key to choose another option...";
getch();
system("cls");

    login();
    system("cls");

	mainmenu:
    system("cls");
    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t*** Welcome to the GYM Management System ***" << endl << endl;
    cout << "\t\t\t\t\t\t\t\t--------------------------------------------" << endl << endl;
    cout << "\t\t\t\t\t\t\t\t<1> Menu" << endl << endl;
    cout << "\t\t\t\t\t\t\t\t<2> Schedule" << endl << endl;
    cout << "\t\t\t\t\t\t\t\t<3> Exit" << endl << endl;
    cout << "\t\t\t\t\t\t\t\t--------------------------------------------" << endl << endl;
    cout << "\t\t\t\t\t\t\t\tEnter Your Choice:\t\t";
    cin >> ch1;
    cout << endl << endl << endl;

    if(ch1 == "1")
    {	menu:
        system("cls");
        cout << "\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t*** Welcome to the Main Menu ***" << endl << endl;
        cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
        cout << "\t\t\t\t\t\t\t\t<1> Enter into Member's DataBase" << endl << endl;
        cout << "\t\t\t\t\t\t\t\t<2> Enter into Employees's DataBase" << endl << endl;
        cout << "\t\t\t\t\t\t\t\t<3> Enter in Monetary Database" << endl << endl;
		cout << "\t\t\t\t\t\t\t\t<4> Go Back" << endl << endl;
        cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
        cout << "\t\t\t\t\t\t\t\tEnter Your choice:     ";
        cin >> ch2;
        
        	if(ch2 == "1")
           	{   memberdatabase:
           		system("cls");
            	cout << "\n\n";
            	cout << "\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t*** Welcome To Members's DataBase ***" << endl << endl;
            	cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
            	cout << "\t\t\t\t\t\t\t\t<1> Add New Member's Information              " << endl << endl;
            	cout << "\t\t\t\t\t\t\t\t<2> Display Member's Information              " << endl << endl;
            	cout << "\t\t\t\t\t\t\t\t<3> Detail OF ALL The Members In The GYM      " << endl << endl;
            	cout << "\t\t\t\t\t\t\t\t<4> Total Number of Members in GYM            " << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<5> Go Back                                   " << endl << endl;
				cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
            	cout << "\t\t\t\t\t\t\t\tEnter your choice:     ";
            	cin >> ch3;
               	
               	if(ch3 == "1")
               	{   system("cls");
              		m1.get_data();
               		goto memberdatabase;
				}
			    else if(ch3 == "2")
               	{   system("cls");
          	        m1.show_data();
			    	cout << "\n";
                	goto memberdatabase;
                }
                else if(ch3 == "3")
                {   system("cls");
                    m1.all_members_data();
                    goto memberdatabase;
				}
					
                else if(ch3 == "4")
                {   m1.total_members();
                    goto memberdatabase;
                }	
                else if(ch3 == "5")
				 	goto menu;

                else
				{   system("cls");
                    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
   					cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
					getch();
                    goto memberdatabase;
                }	
            }
            
            else if(ch2 == "2")
            {   employeedatabase:
           		system("cls");
               	cout << "\n\n";
               	cout << "\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t*** Welcome To Employee's DataBase ***" << endl << endl;
               	cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
               	cout << "\t\t\t\t\t\t\t\t<1> Add New Employee's Information             " << endl << endl;
               	cout << "\t\t\t\t\t\t\t\t<2> Display Employee's Information             " << endl << endl;
               	cout << "\t\t\t\t\t\t\t\t<3> Detail OF ALL The Employees In The GYM     " << endl << endl;
               	cout << "\t\t\t\t\t\t\t\t<4> Total Number of Employees in GYM           " << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<5> Go Back                                   " << endl << endl;
				cout << "\t\t\t\t\t\t\t\t----------------------------------------------" << endl << endl;
               	cout << "\t\t\t\t\t\t\t\tEnter your choice:     ";
               	cin >> ch4;
               	
               	if(ch4 == "1")
               	{   system("cls");
              		e1.get_data();
               		goto employeedatabase;
				}
               	else if(ch4 == "2")
               	{   system("cls");
          	        e1.show_data();
			    	cout << "\n";
                	goto employeedatabase;
                }              
                else if(ch4 == "3")
                {   system("cls");
                    e1.all_employees_data();
                    goto employeedatabase;
				}			
                else if(ch4 == "4")
                {   e1.total_employees();
                    goto employeedatabase;
                }     	
                else if(ch4 == "5")
                   	goto menu;		
                else
				{   system("cls");
                    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
   					cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
					getch();
                    goto employeedatabase;
                }	
            }
            
            else if(ch2 == "3")
            {   get_data:
				system("cls");
				cout << "\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t*** Welcome To Monetary DataBase ***    "<< endl << endl;
				cout << "\t\t\t\t\t\t\t\t--------------------------------------------" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<1> Record fee(member database)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<2> View Recorded Fee(member database)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<3> View members details(member database)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t--------------------------------------------" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<4> Record Payment(employee database)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<5> View Recorded Payment(employee database)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<6> View employees details(employee database)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t--------------------------------------------" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<7> Check and Balance(Overview)" << endl << endl;
				cout << "\t\t\t\t\t\t\t\t<8> Go back" << endl << endl;
				cout << "\t\t\t\t\t\t\t\tEnter your choice:     ";
				cin >> ch5;
		
				if(ch5 == "1")
				{   system("cls");
					m1.record_fee();
					goto get_data;
				}
		        else if(ch5 == "2")
				{   system("cls");
					m1.show_fee();
					goto get_data;
				}
		        else if(ch5 == "3")
				{   system("cls");
					m1.all_members_data();
					goto get_data;
				}
				else if(ch5 == "4")
				{   system("cls");
					e1.record_pay();
					goto get_data;
				}
				else if(ch5 == "5")
				{   system("cls");
					e1.show_pay();
					goto get_data;
				}
				else if(ch5 == "6")
				{   system("cls");
					e1.all_employees_data();
					goto get_data;
				}
				else if(ch5 == "7")
				{
					if(m1.memberfee != 0)
					{   system("cls");
						cout << "\n\n\n\n\n\n\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
						cout << "\t\t\t\t\t\t\t\tTotal Members: " << m1.counter << endl << endl;
						cout << "\t\t\t\t\t\t\t\tMembers that paid fee: " << m1.fee << endl << endl;
						cout << "\t\t\t\t\t\t\t\tTotal Fee Received: " << m1.memberfee << endl << endl;
						cout << "\t\t\t\t\t\t\t\tTotal Employees: " << e1.counter << endl << endl;
						cout << "\t\t\t\t\t\t\t\tEmployees that Received Pay:" << e1.pay << endl << endl;
						cout << "\t\t\t\t\t\t\t\tTotal Payment Given: " << e1.emp_pay_given << endl << endl;
						int total = m1.memberfee - e1.emp_pay_given;
						cout << "\t\t\t\t\t\t\t\tTotal Money Earned: " << total << endl << endl;
						if(total > 0)
						   cout << "\t\t\t\t\t\t\t\tWOW!!! You are in Profit!" << endl << endl;
						else
						   cout << "\t\t\t\t\t\t\t\tAlas!!! You are in Loss!" << endl << endl;
						
						cout << "\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
						cout << "\t\t\t\t\t\t\t\tPress any key to choose another option...";
        				getch();
					}
					else
					{   system("cls");
      					cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\tOOPS!!!!" << endl;
      					cout << "\t\t\t\t\t\t\tNote: No Record To Display plz Go Back And Enter Some Entries...";
      					getch();
					}
					goto get_data;
				}
				else if(ch5 == "8")
				{   system("cls");
					goto menu;
				}
		
				else
				{   system("cls");
					cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
    				cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
					getch();
					goto get_data;
				}
            	goto menu;
			}
            else if(ch2 == "4")
    		    goto mainmenu;

			else
			{   system("cls");
				cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
    			cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
				getch();
				goto menu;
			}
	}	

	else if(ch1 == "2")
	{   schedule:
		s1.show_schedule();
		cout << "\n\n\t\t\t\t\t\t\t\t<1> Reset Schedule" << endl << endl;
		cout << "\t\t\t\t\t\t\t\t<2> Go back" << endl << endl;
		cout << "\t\t\t\t\t\t\t\t---------------------------------------------" << endl << endl;
		cout << "\t\t\t\t\t\t\t\tEnter your choice:     ";
		cin >> ch6;
		if(ch6 == "1")
		{   s1.get_schedule();
			goto mainmenu;
		}
		else if(ch6 == "2")
			goto mainmenu;
		else
		{   system("cls");
			cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
    		cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
			getch();
			goto schedule;
		}
	}
    
 	else if(ch1 == "3")
 	{ system("cls");
	cout<<"\n\n\n\n\n\n\n\n\n\n\n\n\n";
	cout<<"\t\t\t\t\t _______________________________________________________________________________________ \n";
	cout<<"\t\t\t\t\t|                                           		                                |\n";
	cout<<"\t\t\t\t\t|                             THANK YOU FOR USING OUR                                   |\n";
	cout<<"\t\t\t\t\t|                                                                                       |\n";
	cout<<"\t\t\t\t\t|                              GYM MANAGEMENT SYSTEM                                    |\n";
	cout<<"\t\t\t\t\t|_______________________________________________________________________________________|\n";
	cout<<"\n\n\n\n\t\t\t\t\t";
 	}
 	
else
{   system("cls");
    cout << "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\t\t\t\t\t\t\t\t\tWrong Input" << endl;
    cout << "\t\t\t\t\t\t\t\t\tPress any key to choose another option...";
	getch();
    goto mainmenu;
}
return 0;
}
