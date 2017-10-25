FROM microsoft/aspnetcore-build:2.0
EXPOSE 80
WORKDIR /src
COPY BuildingBlocks ./BuildingBlocks
WORKDIR Services/Catalog/Catalog.API
COPY Services/Catalog/Catalog.API .
RUN dotnet publish -c Release -o /app
WORKDIR /app
ENTRYPOINT ["dotnet", "Catalog.API.dll"]
