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

hist(newdata$active_power, col="red", main = "Global Active Power", xlab="Global Active Power (kilowatts)")


dev.copy(png,filename="plot1.png");
dev.off ();
