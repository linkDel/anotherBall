

#ifndef FIRST_H
#define FIRST_H

namespace constants
{
	 inline constexpr double gravity{ 9.8 };
	 inline bool  on_of{true};
	 inline int secondCheck{ 0 };
}

#endif


#include"first.h"
#include<cstdlib>
#include<iostream>

void control()
{
	std::cout << "At " << constants::secondCheck <<
		" seconds, the ball is on the ground.";
	constants::on_of = false;
}

int getTowerHeight()
{
	std::cout << "Enter a tower height:";
	int towerHeight{};
	std::cin >> towerHeight;
	return towerHeight;
}

void howFarTheBallHasFallen(int towerHeight,int seconds)
{	
	constants::secondCheck=seconds;
	double ballHasFallen{towerHeight-(constants::gravity * (seconds * seconds) / 2) };
	if (ballHasFallen > 0)
	
		std::cout << "At " << seconds << " seconds, the ball is at height:"
			<< ballHasFallen << " meters" << '\n';
	else
	{
		if (constants::on_of==true)
			control();
	}
}

int main()
{
	int towerHeight{ getTowerHeight() };
	
	howFarTheBallHasFallen(towerHeight,0);
	howFarTheBallHasFallen(towerHeight,1);
	howFarTheBallHasFallen(towerHeight,2);
	howFarTheBallHasFallen(towerHeight,3);
	howFarTheBallHasFallen(towerHeight,4);
	howFarTheBallHasFallen(towerHeight,5);
	
	return EXIT_SUCCESS;
}
