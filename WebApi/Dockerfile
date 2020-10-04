# This is standard Microsoft .NET Core container
FROM microsoft/dotnet
 
# Copy our code from the "/src/MyWebApi" folder to the "/app" folder in our container
WORKDIR /app
COPY ./src/MyWebAPI .
EXPOSE 80
 
# Restore the necessary packages
RUN dotnet restore
 
# Build and run the dotnet application from within the container
ENTRYPOINT ["dotnet", "run"]
