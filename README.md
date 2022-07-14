(We were the first group to submit a successful final program. Only one other group out the remaining four groups also submitted a successful project.)

TRAFFIC SIMULATION
Version: 1.0
Time Period: ~10hrs
Coders: Ioana Cristescu, Liz Smith, Kevorc Ibrahimian, and Alex Shaw

FRONT END OF THE PROGRAM:
    Traffic Simulation is an animated simulation of a four-way street 
    intersection.
    The visuals of the simulation include: 
    northbound, southbound, eastbound, westbound road lanes
    cars, SUVs, and trucks
    traffic lights (4 independent stationary blocks that change color)
    a display of the number of time ticks that have passed
    When the program is run, with each tick of time, vehicles on the road are 
    expected to behave similarly to normal traffic-- they are meant to stop in 
    time for red lights, approach red lights if they have road remaining before 
    the intersection, continue driving after an intersection (where they should 
    no longer worry about the lights), turn or continue straight, and, lastly, 
    never crash.

BACK END OF THE PROGRAM:
    Whether a new vehicle is generated to visibly enter the road at each time
    tick (if there is room for it), the type of vehicle (car, truck, or SUV), 
    the lane it is on (south, north, east, or westbound), as well as if it will 
    turn right or go straight is randomly generated during the vehicle object's 
    creation.

    When generating, we added 3 spaces before the 
    number_of_sections_before_intersection. This allows the head of a car, suv 
    or truck to generate in the first spot of the seen roadway. Similarly there 
    there invisible spaces at the end of the road that are used to make removing
    vehicles easier. After the intersections the vehicle moves as usual into
    the invisible part of the road until the last part of the vehicle is
    showing. When this occurs the vehicle itself is deleted. As each tick 
    increases and there is nothing in front of the vehicle, we take the caboose 
    or back end of the vehicle and set it equal to the front end of the 
    vehicle + 1 until it reaches the intersection or something appears in front 
    of the vehicle. Then when it comes to the intersection, It has a couple of 
    requirements. The ticks_until_red must be long enough for the vehicle type 
    to make it through. Also, the vehicle type will decide to either keep moving 
    forward or turn right. We created a move forward method to move the car 
    along in the same direction as before the intersection. If it must turn 
    right, we change the direction and road it is placed on when moving the back 
    end of the vehicle. When it comes to updating the positions at each tick, we 
    broke it up into three sections. The first being everything after the 
    intersection, because it had the simplest requirements: as long as there is 
    space in front, move. Next is the intersection itself. If there was space in 
    the intended direction, and there was enough time then it could move, 
    otherwise it would have to wait behind the light. Lastly, there is 
    everything before the intersection, which is similar to the chunk of road 
    after the intersection. It just checks that there is room in front of the 
    car and moves it accordingly. 

INSTALLATION AND COMPILATION:
    To install the traffic simulation software, you must download the tar file 
    containing all of the necessary files for the program and extract them to a 
    directory on your machine. Navigate to this directory in a terminal, then 
    use the command “make” to compile everything. 

RUNNING THE SIMULATION:
    To run the executable created by the makefile, enter the command 
    “./main” with the first command line argument being the file containing all 
    of the inputs for the program, and the second being a seed that is used for 
    random generation. In other words, the line entered in the terminal takes 
    this form: ./main [input file] [seed]
    Example: ./main input_file_format.txt 1893430940.

    Pressing the return key will advance the simulation by 1 tick, until it 
    reaches the max number of ticks and closes out. 

BUILDING AND RUNNING THE TEST:
    To build the test for the simulation, use the same makefile as the simulation.
    The executable is called "catch" and running it would be done using the 
    terminal command "./catch" 
