FROM mcr.microsoft.com/windows/nanoserver:1809

WORKDIR /app/
ADD app/aspnetcoreapp/bin/Release/netcoreapp2.2/aspnetcoreapp.dll .

EXPOSE 8000

ENTRYPOINT ["dotnet", "aspnetcore.dll"]