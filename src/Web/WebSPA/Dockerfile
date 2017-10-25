FROM microsoft/aspnetcore-build:2.0
EXPOSE 80
WORKDIR /src
COPY BuildingBlocks ./BuildingBlocks
WORKDIR Web/WebSPA
COPY Web/WebSPA .
RUN npm rebuild node-sass
RUN dotnet publish -c Release -o /app
WORKDIR /app
ENTRYPOINT ["dotnet", "WebSPA.dll"]
