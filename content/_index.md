---
# Leave the homepage title empty to use the site title
title: ''
summary: ''
date: 2026-01-05
type: landing

design:
  # Default section spacing
  spacing: '0'

sections:
  # Developer Hero - Gradient background with name, role, social, and CTAs
  - block: dev-hero
    id: hero
    content:
      username: me
      greeting: "Hi, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I deliver"
        strings:
          - "strategic technical insight"
          - "data-driven decision support"
          - "specialized mechanical design"
          - "innovative system architecture"
        type_speed: 70
        delete_speed: 40
        pause_time: 2500
      cta_buttons:
        - text: View My Work
          url: "#projects"
          icon: arrow-down
        - text: Get In Touch
          url: "#contact"
          icon: envelope
    design:
      style: centered
      avatar_shape: circle
      animations: true
      background:
        color:
          light: "#fafafa"
          dark: "#0a0a0f"
      spacing:
        padding: ["6rem", "0", "4rem", "0"]
  
  # Filterable Portfolio - Alpine.js powered project filtering
  - block: portfolio
    id: projects
    content:
      title: "Featured Projects"
      subtitle: "A selection of my recent work"
      count: 0
      filters:
        folders:
          - projects
      buttons:
        - name: All
          tag: '*'
        - name: Machine Learning
          tag: Machine Learning
        - name: Sales Engineering
          tag: Sales Engineering
        - name: Mechanical Engineering
          tag: Mechanical Engineering
      default_button_index: 0
      # Archive link auto-shown if more projects exist than 'count' above
      # archive:
      #   enable: false  # Set to false to explicitly hide
      #   text: "Browse All"  # Customize text
      #   link: "/work/"  # Custom URL
    design:
      columns: 3
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Visual Tech Stack - Icons organized by category
  - block: tech-stack
    id: skills
    content:
      title: "Tech Stack"
      subtitle: "Technologies I use to build things"
      categories:
        - name: Languages
          items:
            - name: Java
              icon: devicon/java
            - name: Python
              icon: devicon/python
            - name: Rust
              icon: devicon/rust
            - name: MATLAB
              icon: devicon/matlab
        - name: CAD
          items:
            - name: SolidWorks
              icon: brand/solidworks
            - name: AutoDesk Inventor
              icon: brand/autodesk
        - name: Backend
          items:
            - name: Node.js
              icon: devicon/nodejs
            - name: SQL
              icon: devicon/sql
        - name: DevOps
          items:
            - name: Docker
              icon: devicon/docker
            - name: AWS
              icon: devicon/amazonwebservices-wordmark
            - name: GitHub Actions
              icon: brands/github
    design:
      style: grid
      show_levels: false
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # Experience Timeline
  - block: resume-experience
    id: experience
    content:
      title: Experience
      date_format: Jan 2006
      items:
        - title: Sales Engineer
          company: AST
          company_url: 'https://ast-inc.com/'
          company_logo: ''
          location: Tacoma, WA
          date_start: '2025-07-07'
          date_end: ''
          description: |2-
            * Directly supported $11.5M in total contract value (TCV) across 7 major capital equipment projects
            * Develop technical proposals and compliance matrices for capital equipment sales and SCRs
            * Map customer User Requirement Specifications (URS) to system capabilities to verify cGMP compliance
            * Create system layouts and 3D concept models using Autodesk Inventor for cleanroom integration
            # * Execute Epicor quotes and participate in pre-sales technical reviews and on-site customer visits
        - title: Mechanical Engineer
          company: Beck Engineering
          company_url: ''
          company_logo: ''
          location: Gig Harbor, WA
          date_start: '2017-06-01'
          date_end: '2020-08-31'
          description: |2-
            * Developed detailed 3D CAD models and engineering drawings using SolidWorks for production
            * Co-developed a Finite Element Analysis (FEA) application in Visual Basic for structural simulations
            * Automated engineering workflows using MATLAB, Visual Basic, Fortran, G-Code, and LabVIEW
            * Performed complex mechanical calculations involving thermodynamics and mechanics
            * Conducted hands-on prototyping and testing to validate design concepts and system reliability
        - title: Service Lot Attendant
          company: Haselwood Buick, Pontiac, GMC
          company_url: ''
          company_logo: ''
          location: Bremerton, WA
          date_start: '2009-07-01'
          date_end: '2010-03-01'
          description: |2-
            * Managed vehicle flow and inventory documentation for a high-volume dealership
            * Supported service technicians with parts delivery and vehicle placement
            * Performed basic vehicle inspections including fluid levels and tire pressure
        - title: Waiter / Host
          company: McCormick & Schmick's
          company_url: ''
          company_logo: ''
          location: Austin, TX
          date_start: '2008-06-01'
          date_end: '2009-06-30'
          description: |2-
            * Provided fine dining service, managing seafood menu explanations and guest special requests
            * Coordinated table assignments and reservations to optimize service flow during peak hours
            * Handled transaction processing and resolved guest inquiries professionally
        - title: Advanced Network Services / Business Support
          company: AT&T
          company_url: ''
          company_logo: ''
          location: Bothell, WA
          date_start: '2006-11-01'
          date_end: '2008-01-01'
          description: |2-
            * Provided technical support for business connectivity issues, resolving 30+ inquiries daily
            * Achieved >95% positive call scores for high-quality technical troubleshooting
            * Resolved billing discrepancies and managed corporate account reconciliations
        - title: Automotive Detail QC Specialist
          company: Scottsdale Jaguar Land Rover Bentley Rolls Royce
          company_url: ''
          company_logo: ''
          location: Scottsdale, AZ
          date_start: '2005-07-01'
          date_end: '2006-08-31'
          description: |2-
            * Conducted quality control inspections on exotic and luxury vehicles to meet stringent cosmetic standards
            * Managed documentation for delivery logs, service records, and inspection reports
            * Coordinated with detailing teams to ensure exceptional vehicle presentation for client handover
        - title: Waiter / Server
          company: Merrill Gardens
          company_url: ''
          company_logo: ''
          location: Gig Harbor, WA
          date_start: '2004-05-01'
          date_end: '2005-07-01'
          description: |2-
            * Provided compassionate dining service in an assisted living environment
            * Coordinated with healthcare teams to strictly follow resident dietary requirements and restrictions
            * Maintained high safety and sanitation standards in food handling
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # # Recent Blog Posts
  # - block: collection
  #   id: blog
  #   content:
  #     title: Recent Posts
  #     subtitle: 'Thoughts on web development, tech, and more'
  #     text: ''
  #     filters:
  #       folders:
  #         - blog
  #       exclude_featured: false
  #     count: 3
  #     order: desc
  #   design:
  #     view: card
  #     columns: 3
  #     background:
  #       color:
  #         light: "#f5f5f5"
  #         dark: "#08080c"
  #     spacing:
  #       padding: ["4rem", "0", "4rem", "0"]
  
  # Contact Section
  - block: contact-info
    id: contact
    content:
      title: Get In Touch
      subtitle: "Let's build something amazing together"
      text: |-
        I'm always interested in hearing about new projects and opportunities.
        Whether you're looking to hire, collaborate, or just want to say hi, feel free to reach out!
      email: contact@DeanAllenKelley.com
      autolink: true
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
  
  # CTA Card
  - block: cta-card
    content:
      title: "Open to Opportunities"
      text: |-
        I'm not currently looking for engineering roles, however I am always open to hear about opportunities.
        
        Let's connect and discuss how I can help your team.
      button:
        text: 'Download Resume'
        url: /uploads/Sales_Engineer_Resume_v3.pdf
        new_tab: true
    design:
      card:
        # Light mode: soft pastel theme gradient | Dark mode: rich deep gradient
        css_class: 'bg-gradient-to-br from-primary-200 via-primary-100 to-secondary-200 dark:from-primary-600 dark:via-primary-700 dark:to-secondary-700'
        text_color: dark
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "6rem", "0"]
---
