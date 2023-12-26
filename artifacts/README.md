# UnifiedArtifact npm Package

## Overview
Welcome to the UnifiedArtifact npm package. This package serves as a showcase, demonstrating how 
npm packages can be effectively used to introduce versioning to process artifacts. It provides a centralized hub for 
sharing a consistent artifact base across development projects, simplifying versioning, streamlining collaboration, and enhancing dependency management.

## Key Benefits
- **Version Consistency:** Ensure uniform versioning across projects for a cohesive development experience.
- **Artifact Sharing:** Share a common foundation for projects, fostering collaboration and reliability.
- **Seamless Integration:** Easily integrate UnifiedArtifact into your development workflow for consistent results.

## How to Use
1. Install the npm package: `npm install unified-artifact`
2. Access JSON files directly: `const artifact = require('unified-artifact/your-file.json');`

## Customize
- The current setup of this project is such that only the contents of the element-templates folder are being published in the npm package. This of course can be andjusted to ones needs to inlcude all relevant files.
- To include different folders or files, modify the `files` property in the package.json file accordingly.

## License
This repository is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Maintainer
Amin Yacine <amin.yacine@miragon.io>
