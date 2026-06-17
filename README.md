# minor-2-project-SmartFileAnalyzer-
🧠 Smart File & Image Analyzer
A powerful, AI-driven desktop application built to intelligently manage local storage. This tool goes beyond basic file properties by leveraging deep learning for facial clustering, demographic analysis, and semantic context—all orchestrated by an integrated AI Copilot.

✨ Key Features
🤖 AI Copilot Workspace: An integrated chat assistant powered by Semantic Kernel and the Gemini API. You can use natural language (e.g., "Scan my downloads folder") to trigger UI actions, scan directories, and generate reports.

👥 Facial Identity Clustering: Utilizes FaceRecognitionDotNet (Dlib) to detect human faces in local image directories, extract facial encodings, and automatically group photos of the same individual together without requiring prior training data.

📊 Demographic Filtering: Integrates OpenCvSharp and a pre-trained Caffe DNN model to perform on-device gender classification for detected faces, allowing dynamic sorting and filtering in the UI.

🔍 Exact Deduplication Engine: A highly parallelized scanning engine that uses MD5 hashing and file size grouping to find exact duplicate files with minimal memory overhead.

🖼️ Interactive Media Previews: A built-in, lightweight media viewer with smart navigation to seamlessly review clustered images.

🔐 Local Authentication: Secure, offline user account management and administrative dashboards powered by SQLite and Entity Framework Core.

🛠️ Technology Stack
Framework: .NET 8

Architecture: Windows Presentation Foundation (WPF) / MVVM Pattern

Language: C#

Database: SQLite via Entity Framework Core

AI Integration: Microsoft Semantic Kernel

Computer Vision: * OpenCvSharp4

FaceRecognitionDotNet (Dlib)

UI/UX Framework: MaterialDesignThemes in XAML

🚀 Getting Started
Prerequisites
Visual Studio 2022 (or newer) with the .NET desktop development workload installed.

.NET 8 SDK.

Required AI Models
For the facial recognition and demographic filtering pipelines to function locally, you must download the following pre-trained models and place them in a Models folder at the root of your executable directory (the .csproj is configured to copy them to the output directory):

dlib_face_recognition_resnet_model_v1.dat

mmod_human_face_detector.dat

deploy_gender.prototxt

gender_net.caffemodel

Installation
Clone the repository:

Bash
git clone https://github.com/YourUsername/SmartFileAnalyzer.git
Open SmartFileAnalyzer.sln in Visual Studio.

Add your Gemini API key inside Services/AIAgentManager.cs.

Restore NuGet packages.

Build and run the project (Press F5). The SQLite database will automatically be generated on the first launch.

📁 Project Architecture
The application strictly adheres to the Model-View-ViewModel (MVVM) pattern utilizing the CommunityToolkit.Mvvm library to ensure clean separation of concerns:

Models / Data: Defines UserAccount schemas and the EF Core AppDbContext.

ViewModels: Handles the business logic, state management, and ICommand bindings (e.g., MainViewModel).

Views: Contains the XAML UI layouts (MainWindow, LoginWindow, ImagePreviewWindow).

Services & Plugins: Houses the core engines, including the FileAnalyzerPlugin which acts as the bridge between native UI commands and Semantic Kernel AI triggers.

🎓 Academic Context
This application was developed as a Minor Project-II under the Department of Computer Science & Engineering at the Sri Aurobindo Institute of Technology.

Developer: Neeraj Yadav

Project Guide: Prof. Shivangi Chuhan  
