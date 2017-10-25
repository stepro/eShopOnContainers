FROM microsoft/aspnetcore-build:2.0
EXPOSE 80
WORKDIR /src
COPY BuildingBlocks ./BuildingBlocks
WORKDIR Services/Catalog/Catalog.API
COPY Services/Catalog/Catalog.API .
ENV ASPNETCORE_ENVIRONMENT Development
ENV ConnectionString Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word
ENV PicBaseUrl http://localhost:5101/api/v1/catalog/items/[0]/pic/
ENV EventBusConnection=rabbitmq \
    UseCustomizationData=True \
    AzureServiceBusEnabled=False \
    AzureStorageEnabled=False
RUN dotnet publish -c Release -o /app
WORKDIR /app
ENTRYPOINT ["dotnet", "Catalog.API.dll"]
