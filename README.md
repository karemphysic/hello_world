# hello_world
new repository

I Made an code to convert  mat file of "Trend" Grid 2D martix  to xyz in CSV file, but i have a problem with matrix dimension 
the code;

load ('trend.mat')

[lon,lat] = size(trend);           % Where X = 360   &  Y = 180 the dimension of matrix

    lon=0.5:359.5;      
    lat=89.5:-1:-89.5;
    
tws = trend;

file = fopen('Trend.csv','w');
for y = 1 : 180
	for x = 1: 360
		
		fprintf(file, strcat(num2str(lat(y)),',',num2str(lon(x)),','));
		
			fprintf(file, '%.16g,',tws(x,y));			

		fprintf(file,'\n');
	end;
end;
fclose(file);
