## What this MCP server does (in human terms)

The MCP Umbraco Package Suggestor acts like a senior Umbraco architect sitting next to your codebase 👀

It:

**Scans your actual Umbraco / .NET project**

**Understands:**
- Your content structure
- Your architectural patterns
- Your business domain

**Then intelligently suggests packages that actually make sense for your project**

Not generic "top downloads".
Not random marketplace scrolling.

**Context-aware recommendations.**

### Why this is different from the Marketplace

The Umbraco Marketplace answers:
> "What packages exist?"

This tool answers:
> "Which packages should you care about — and why?"

#### Examples:
- You use many Blocks → suggests block-enhancing packages
- Heavy content editors → suggests editor UX helpers
- Custom workflows → suggests governance & approval tools
- Multisite / multilingual → suggests scaling & management helpers

👉 It turns the Marketplace from a catalog into an **intelligent advisor**.

### The real value for the community 💙

 **Hidden gems get discovered**
> Small but brilliant packages finally reach the right projects.

 **Lower cognitive load for developers**
> No more "Did we miss a package that already solves this?"

 **Faster project setup & better architecture**
> Especially for new teams or large Umbraco solutions.

 **Healthier Umbraco ecosystem**
> More usage → more feedback → more maintained packages.

### Why MCP is the perfect fit here

This isn't an editor feature.
This isn't content tooling.

This is a **technical intelligence layer:**

- Reads code
- Understands patterns
- Compresses complexity
- Suggests better decisions

Exactly what MCP is meant for.

> "An AI-powered MCP server that understands your Umbraco project and recommends the right community packages — so great tools don't stay hidden."

## Key Features

- **Intelligent Project Analysis**: Deep-dive analysis of your Umbraco codebase including architecture patterns, code complexity, and business logic
- **AI-Powered Recommendations**: LLM-driven package suggestions based on your project's specific needs
- **Marketplace Intelligence**: Comprehensive search across NuGet and Umbraco Marketplace
- **Integration Guidance**: Context-aware integration hints and implementation steps
- **Performance Simulation**: "What-if" scenarios showing potential impact of adding packages
- **Enterprise Insights**: Advanced architectural assessment and strategic recommendations


### Package Analysis Tools

#### `SuggestPackages`
Analyzes a .NET/Umbraco project and suggests relevant packages with detailed reasoning.

#### `GenerateMarketplaceMap`
Creates an AI-driven marketplace map visualization, ranking packages by relevance, popularity, compatibility, and community score.


#### `PerformDeepProjectAnalysis`
Performs sophisticated deep-dive analysis of your Umbraco project, providing enterprise-level insights on architecture, code quality, performance, and strategic recommendations.


### Package Integration Tools

#### `SimulatePackageImpact`
Simulates "what-if" scenarios showing how your site would perform if certain packages are added.


#### `GetCodeIntegrationHints`
Provides intelligent, context-aware code integration hints based on your actual Umbraco project structure.

## Installation

1. **Prerequisites**
   - .NET 10.0 or later
   - Access to NuGet and Umbraco Marketplace APIs

2. **Build the project**
   ```bash
   dotnet build
   ```

3. **Run the MCP server**
   ```bash
   dotnet run
   ```

## Usage with MCP Clients

This server implements the Model Context Protocol and can be used with any MCP-compatible client. The server communicates via stdio and automatically discovers available tools.


```

## Response Formats

### Package Suggestions Response
```json
{
  "DeepProjectAnalysis": {
    "ProjectOverview": {
      "Framework": ".NET 8.0",
      "UmbracoVersion": "13.0.0",
      "TotalCodeFiles": 45,
      "TotalLinesOfCode": 12500,
      "DetectedFeatures": ["Content Management", "E-commerce"],
      "BusinessDomain": ["Retail", "Content Publishing"],
      "ArchitecturePatterns": ["Layered Architecture", "Repository Pattern"]
    },
    "ArchitecturalAssessment": {
      "ArchitectureStyle": "Layered",
      "LayerCompleteness": {
        "HasPresentationLayer": true,
        "HasBusinessLayer": true,
        "HasDataLayer": true,
        "HasServiceLayer": false
      }
    }
  },
  "PackageRecommendations": [
    {
      "Package": {
        "PackageId": "Umbraco.Forms",
        "PackageName": "Umbraco Forms",
        "Description": "Create forms in Umbraco",
        "RelevanceScore": 0.92,
        "CommunityScore": 0.85
      },
      "WhyRecommended": {
        "Reason": "Based on your contact forms and data collection needs",
        "BusinessValue": "Streamlines lead generation and user engagement"
      }
    }
  ]
}
```

## Architecture

The server consists of several key components:

- **McpServerSetup.cs**: Configures the MCP server with dependency injection
- **PackageSearchTools.cs**: Handles NuGet and marketplace searches
- **PackageAnalysisTools.cs**: Provides AI-powered analysis and recommendations
- **PackageIntegrationTools.cs**: Offers integration guidance and impact simulation
- **ProjectAnalyzer.cs**: Analyzes .NET/Umbraco project structure
- **RecommendationEngine.cs**: Generates intelligent package recommendations
- **NuGetApiClient.cs**: Interfaces with NuGet API
- **UmbracoMarketplaceClient.cs**: Interfaces with Umbraco Marketplace API

## Dependencies

- ModelContextProtocol 0.6.0-preview.1
- Microsoft.Extensions.Hosting 8.0.0
- Microsoft.Extensions.Http 8.0.0
- System.Text.Json 10.0.1
- Microsoft.Extensions.AI (for LLM integration)

## Target Framework

- .NET 10.0

## Development

To extend the server with new tools:

1. Create a new static class with `[McpServerToolType]` attribute
2. Add static methods with `[McpServerTool]` attribute and `[Description]` for parameters
3. Register any required services in `McpServerSetup.ConfigureServices()`


