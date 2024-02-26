
Frequently Asked Questions (FAQs)
==================================

1. **How should we manage repositories for Chatbot?**
   - Organize repositories based on modules:
     - Chatbot Backend
     - NLP Engine (Gen AI)
     - Terraform scripts for Deployments
     - Knowledge Content

2. **How should we scale our infrastructure?**
   - Evaluate scaling strategies based on demand and growth patterns.
   - Consider horizontal scaling for adding more nodes or vertical scaling for enhancing existing nodes.

3. **Should we use Network Load Balancer or Application Load Balancer?**
   - Decide based on specific requirements:
     - Network Load Balancer (NLB) for even traffic distribution.
     - Application Load Balancer (ALB) for advanced routing, SSL termination, and content-based routing.

4. **How should we scale Vector Database Infrastructure?**
   - Assess growth patterns and scaling needs.
   - Implement horizontal scaling by adding more nodes or vertical scaling by enhancing existing nodes.

Should we use a common GenAI module for all Chatbots?
---------------------

   - Evaluate the benefits, considering performance, customization, and maintenance implications.

How to manage infrastructure?
-------------------
   - Implement version control for infrastructure-as-code scripts.
   - Ensure proper documentation for onboarding and troubleshooting.

7. **How to monitor the health of infrastructure?**
   - Use tools like AWS CloudWatch to monitor health.
   - Set up alarms for critical metrics, e.g., EC2 instances utilization.

8. **How to monitor our APIs?**
   - Employ API monitoring tools to track response times, error rates, and overall health.

9. **How to identify performance bottlenecks?**
   - Conduct regular performance testing.
   - Utilize profiling tools and metrics to pinpoint areas of improvement.



.. autosummary::
   :toctree: generated

   lumache
