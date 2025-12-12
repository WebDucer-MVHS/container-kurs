# Image für Build
FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
# Verzeichnis für das Build
WORKDIR /build
# Kopiere das Projekt in das Arbeitsverzeichnis
COPY . ./
# Wiederherstellen der Abhängigkeiten
RUN dotnet restore
# Veröffentlichen der App in das Verzeichnis /app
RUN dotnet publish BlazorWebAppMovies.csproj -c Release -o /app

# Image für Runtime
FROM mcr.microsoft.com/dotnet/aspnet:9.0-alpine
# Labels
LABEL version=1.0.0
LABEL build_date=2024-12-01
LABEL dotnet_version=9.0
LABEL author=MVHS
# Verzeichnis für die App
WORKDIR /app
# Kopieren des aus dem Build zu Runtime Image
COPY --from=build /app .
# Datenbank Connection string
ENV CONNECTIONSTRINGS__BLAZORWEBAPPMOVIESCONTEXT=""
# Port für Webserver
EXPOSE 8080
# App in Container starten
ENTRYPOINT ["dotnet", "BlazorWebAppMovies.dll"]
