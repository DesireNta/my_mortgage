FROM microsoft/dotnet:2.0-sdk AS builder
WORKDIR /app
COPY /src/optimizer.csproj /app
RUN dotnet restore
COPY /src /app
RUN dotnet publish -o output
FROM microsoft/aspnetcore:2.0
COPY --from=builder /app/output /app
WORKDIR /app
EXPOSE 80/tcp
ENTRYPOINT ["dotnet"]
CMD ["optimizer.dll"]
