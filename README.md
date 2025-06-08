# Job Search Assistant 🔍

A comprehensive AI-powered job search assistant built with CrewAI that helps you find relevant job opportunities, develop required skills, prepare for interviews, and optimize your career applications.

## 🚀 Features

- **Multi-Agent System**: Four specialized AI agents working together
- **Real-time Job Search**: Fetches current job listings using Adzuna API
- **Skills Analysis**: Identifies required skills and provides development recommendations
- **Interview Preparation**: Generates role-specific interview questions and mock scenarios
- **Career Advisory**: Offers resume optimization and LinkedIn profile enhancement tips
- **Rate Limiting**: Built-in API rate limiting to respect service quotas
- **Detailed Output**: Saves formatted results to file for future reference

## 🤖 AI Agents

### 1. Job Searcher Agent
- **Role**: Searches for job opportunities in your field
- **Goal**: Find relevant positions and highlight key skill requirements
- **Tools**: Adzuna Job Search API integration

### 2. Skills Development Advisor
- **Role**: Analyzes skill requirements from job listings
- **Goal**: Provides actionable recommendations for skill development
- **Output**: Course suggestions, certifications, and practical experience tips

### 3. Interview Preparation Coach
- **Role**: Prepares you for job interviews
- **Goal**: Creates mock interviews and communication strategies
- **Output**: Role-specific questions, presentation tips, and practice scenarios

### 4. Career Advisor
- **Role**: Optimizes your job application materials
- **Goal**: Enhances resume, LinkedIn profile, and networking strategies
- **Output**: Templates, optimization tips, and application best practices

## 🛠️ Technology Stack

- **CrewAI**: Multi-agent orchestration framework
- **Google Gemini 2.0 Flash**: Large Language Model for AI agents
- **Adzuna API**: Real-time job search data
- **LangChain**: Tool integration and LLM management
- **Python**: Core programming language

## 📋 Prerequisites

- Python 3.8 or higher
- API keys for:
  - Google Gemini API
  - Adzuna Job Search API

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/naakaarafr/Job-Search-Assistant.git
   cd Job-Search-Assistant
   ```

2. **Install required packages**
   ```bash
   pip install crewai langchain-google-genai requests tenacity google-api-core
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the project root:
   ```env
   GOOGLE_API_KEY=your_google_gemini_api_key_here
   ADZUNA_APP_ID=your_adzuna_app_id_here
   ADZUNA_API_KEY=your_adzuna_api_key_here
   ```

## 🔑 API Setup

### Google Gemini API
1. Visit [Google AI Studio](https://aistudio.google.com/)
2. Create a new project or select existing one
3. Generate an API key
4. Add the key to your `.env` file

### Adzuna API
1. Visit [Adzuna Developer Portal](https://developer.adzuna.com/)
2. Create a free account
3. Register a new application
4. Get your App ID and API Key
5. Add both to your `.env` file

## 🚀 Usage

1. **Run the application**
   ```bash
   python crew.py
   ```

2. **Follow the interactive prompts**
   - Enter the job role you're looking for (e.g., "Senior Data Scientist")
   - Specify your preferred location (e.g., "New York", "Remote")
   - Optionally provide additional requirements

3. **Wait for results**
   - The system will process your request using all four agents
   - Results are displayed in the terminal and saved to `task_output.txt`

## 📁 Project Structure

```
job-search-assistant/
├── agents.py          # AI agent definitions and configurations
├── config.py          # API configuration and rate limiting settings
├── crew.py           # Main application entry point and crew orchestration
├── tasks.py          # Task definitions for each agent
├── tools.py          # Job search API integration tools
├── task_output.txt   # Generated results file (created after first run)
├── .env              # Environment variables (create this file)
└── README.md         # This file
```

## ⚙️ Configuration

### Rate Limiting
The application includes built-in rate limiting to respect API quotas:

- **Max Requests per Minute**: 15 (configurable in `config.py`)
- **Request Delay**: 4 seconds between requests
- **Agent RPM Limit**: 5 requests per minute per agent
- **Crew RPM Limit**: 10 requests per minute overall

### Job Search Parameters
- **Default Results**: 5 job listings per search
- **Timeout**: 30 minutes maximum execution time
- **Retry Logic**: Automatic retry on rate limit errors

## 📊 Output Format

The application generates professionally formatted output with:

- 🔍 **Job Search Results**: Detailed job listings with company, location, and key skills
- 🎯 **Skills Analysis**: Skill breakdown by job with development recommendations
- 🎤 **Interview Preparation**: Role-specific questions and mock interview scenarios
- 💼 **Career Advisory**: Resume templates and LinkedIn optimization tips

## 🔧 Troubleshooting

### Common Issues

1. **Rate Limit Errors**
   - The system automatically handles rate limits with exponential backoff
   - If errors persist, increase the `REQUEST_DELAY` in `config.py`

2. **API Key Issues**
   - Ensure all API keys are correctly set in the `.env` file
   - Verify API key permissions and quotas

3. **No Job Results**
   - Try broader search terms or different locations
   - Check if the Adzuna API is accessible in your region

4. **Memory Issues**
   - Reduce `NUM_RESULTS` in `config.py` for smaller searches
   - Close other applications to free up memory

## 📈 Customization

### Adding New Agents
1. Create new agent function in `agents.py`
2. Define corresponding task in `tasks.py`
3. Add agent to the crew in `crew.py`

### Modifying Output Format
- Edit task descriptions in `tasks.py`
- Customize the `callback_function` for different file formats
- Adjust formatting templates in task descriptions

### Changing APIs
- Replace or add new tools in `tools.py`
- Update agent tool assignments in `agents.py`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and commit: `git commit -m 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [CrewAI](https://github.com/joaomdmoura/crewAI) for the multi-agent framework
- [Adzuna](https://www.adzuna.com/) for providing job search API
- [Google](https://ai.google.dev/) for the Gemini AI model
- [LangChain](https://langchain.com/) for LLM integration tools

## 📞 Support

If you encounter any issues or have questions:

1. Check the troubleshooting section above
2. Review the API documentation for Gemini and Adzuna
3. Create an issue in the GitHub repository
4. Contact: naakaarafr

## 🔮 Future Enhancements

- [ ] Support for additional job search APIs
- [ ] Email notifications for new job matches
- [ ] Integration with applicant tracking systems
- [ ] Salary analysis and negotiation tips
- [ ] Company culture and reviews integration
- [ ] Automated application submission
- [ ] Progress tracking dashboard

---

**Happy Job Hunting! 🎯**

*Built with ❤️ by naakaarafr*
