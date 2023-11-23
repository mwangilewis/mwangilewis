
% Constants (as previously defined)
initial_velocity = 390;  % m/s
launch_angle = 40;      % degrees
caliber = 0.009;        % m
mass_of_gun = 4;        % kg
distance = 91;          % m
g = 9.81;               % m/s^2 (acceleration due to gravity)
 
% Convert launch angle to radians
launch_angle = deg2rad(launch_angle);
 
% Calculate time of flight
time_of_flight = (2 * initial_velocity * sin(launch_angle)) / g;
 
% Time vector
t = linspace(0, time_of_flight, 1000);
 
% Calculate x and y coordinates of the trajectory
x = initial_velocity * cos(launch_angle) * t;
y = initial_velocity * sin(launch_angle) * t - 0.5 * g * t.^2;
 
% Calculate velocity as a function of time
v = initial_velocity - g * t;
 
% Create a figure
figure;
 
% Plot velocity against time
subplot(2, 1, 1);
plot(t, v);
xlabel('Time (s)');
ylabel('Velocity (m/s)');
title('Bullet Velocity vs. Time');
grid on;
 
% Plot the trajectory
subplot(2, 1, 2);
plot(x, y);
xlabel('Horizontal Distance (m)');
ylabel('Vertical Distance (m)');
title('Bullet Trajectory');
grid on;
