# Data-Science---Exploratory-Data-Analysis----Project-1

hw1 = read.table("household_power_consumption.txt",
	sep =";", 
	col.names =
	c("Date","Time","Global_active_power","Global_reactive_power","Voltage","Global_intensity",
	"Sub_metering_1","Sub_metering_2","Sub_metering_3"),
	fill=FALSE,
	strip.white=TRUE)


hw1$NewDate = as.Date(hw1$Date, format = "%d/%m/%Y")
newdata = subset(hw1, NewDate >= "2007-02-01" & NewDate <= "2007-02-02" ) 

newdata$active_power = as.numeric(paste(newdata$Global_active_power))

plot(newdata$active_power, type= "l", ylab = "Global Active Power (kilowatts)", xlab ="",xaxt='n')
axis(1, at=seq(1,2880,by=1439),
labels=c("Thur","Fri","Sat"), las = 2)

dev.copy(png,filename="plot2.png");
dev.off ();

