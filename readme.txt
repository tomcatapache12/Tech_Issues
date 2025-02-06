
# Define input and output files
$inputFile = "urls.txt"
$outputFile = "result.txt"

# Create the output file if it doesn't exist (or clear it if it exists)
if (-not (Test-Path $outputFile)) {
    New-Item -Path $outputFile -ItemType File
} else {
    # Clear the output file if it exists
    Clear-Content -Path $outputFile
}

# Read each URL from urls.txt and check status
Get-Content $inputFile | ForEach-Object {
    $url = $_
    try {
        # Make the request
        $response = Invoke-WebRequest -Uri $url -Method GET -UseBasicParsing
        # Output 200 URLs
        "$url returned $($response.StatusCode)" | Out-File -Append $outputFile
    }
    catch {
        # If there's an error, output the failed request
        "$url failed with error: $($_.Exception.Message)" | Out-File -Append $outputFile
    }
}

# Output location of result file
Write-Output "Results saved to $outputFile"
