# Use a GCC image to compile C++
FROM gcc:latest

# Set the working directory
WORKDIR /usr/src/app

# Copy the app.cpp file into the container
COPY app.cpp .

# Compile the application
RUN g++ -o myapp app.cpp

# Run the application when the container starts
CMD ["./myapp"]