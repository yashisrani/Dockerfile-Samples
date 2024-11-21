# Use .NET SDK for build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build

# Set working directory
WORKDIR /app

# Copy project files
COPY *.csproj ./
RUN dotnet restore

# Copy the rest of the app
COPY . ./
RUN dotnet publish -c Release -o /publish

# Use a runtime image for deployment
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /publish
COPY --from=build /publish .

# Run the application
ENTRYPOINT ["dotnet", "YourAppName.dll"]

# Expose the port
EXPOSE 5000
