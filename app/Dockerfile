FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
WORKDIR /app

FROM microsoft/dotnet:2.2-sdk AS build
WORKDIR /src
COPY aspnetcoreapp/aspnetcoreapp.csproj aspnetcoreapp/
RUN dotnet restore aspnetcoreapp/aspnetcoreapp.csproj
WORKDIR /src/aspnetcoreapp/
COPY aspnetcoreapp/ .
RUN dotnet build aspnetcoreapp.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish aspnetcoreapp.csproj -c Release -o /app

FROM base AS final
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "aspnetcoreapp.dll"]