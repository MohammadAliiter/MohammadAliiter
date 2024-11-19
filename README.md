import { Badge, Button, Card, Flex, Grid, Heading, Image, Link, Text } from '@/components/ui'
import { GitHubIcon, LinkedInIcon, YouTubeIcon, MailIcon } from '@/components/icons'
import { LanguageCard, ProjectCard, StatsCard } from '@/components/custom'

export default function GitHubProfile() {
  return (
    <Flex direction="column" align="center" className="bg-gradient-to-r from-gray-900 to-blue-900 text-white p-8">
      <Image
        src="https://avatars.githubusercontent.com/u/your-username"
        alt="Mohammad Ali"
        className="rounded-full w-32 h-32 mb-4 border-4 border-blue-500"
      />
      <Heading level={1} className="text-4xl font-bold mb-2">Mohammad Ali</Heading>
      <Text className="text-xl mb-4">Passionate Software Developer | Backend Enthusiast | Frontend Explorer</Text>
      
      <Flex gap={4} className="mb-8">
        <Link href="https://linkedin.com/in/m-ali09" target="_blank">
          <Button variant="outline" leftIcon={<LinkedInIcon />}>LinkedIn</Button>
        </Link>
        <Link href="https://www.youtube.com/c/webxlearner" target="_blank">
          <Button variant="outline" leftIcon={<YouTubeIcon />}>YouTube</Button>
        </Link>
        <Link href="mailto:iter.mohammad01@gmail.com">
          <Button variant="outline" leftIcon={<MailIcon />}>Email</Button>
        </Link>
      </Flex>

      <Card className="w-full mb-8 bg-gray-800 bg-opacity-50">
        <Heading level={2} className="text-2xl font-semibold mb-4">🚀 About Me</Heading>
        <Text>
          Greetings! I'm Mohammad Ali, a software developer with a passion for creating innovative solutions. 
          Currently, I'm diving deep into Backend Development while also exploring Advanced Frontend Frameworks. 
          I'm the creator of <Link href="https://codelutoo.com" className="text-blue-400 hover:underline">Codelutoo</Link>, 
          a platform offering free frontend components and templates.
        </Text>
      </Card>

      <Grid cols={2} gap={4} className="w-full mb-8">
        <ProjectCard
          title="Codelutoo"
          description="A platform providing free frontend components and templates."
          link="https://codelutoo.com"
          tags={['React', 'Node.js', 'MongoDB']}
        />
        <ProjectCard
          title="WebX Learner"
          description="YouTube channel for programming tutorials and tech insights."
          link="https://www.youtube.com/c/webxlearner"
          tags={['Education', 'Web Development', 'Tutorials']}
        />
      </Grid>

      <Card className="w-full mb-8 bg-gray-800 bg-opacity-50">
        <Heading level={2} className="text-2xl font-semibold mb-4">🛠️ Tech Stack</Heading>
        <Flex wrap gap={2}>
          {['React', 'Node.js', 'MongoDB', 'JavaScript', 'TypeScript', 'Redux', 'Tailwind CSS', 'Bootstrap', 'MySQL', 'Java', 'HTML5', 'CSS3', 'Postman', 'Photoshop'].map((tech) => (
            <Badge key={tech}>{tech}</Badge>
          ))}
        </Flex>
      </Card>

      <Grid cols={3} gap={4} className="w-full mb-8">
        <StatsCard
          title="GitHub Stats"
          stat={<GitHubStatsWidget username="mohammadaliiter" />}
        />
        <StatsCard
          title="Streak Stats"
          stat={<GitHubStreakWidget username="mohammadaliiter" />}
        />
        <StatsCard
          title="Top Languages"
          stat={<GitHubLanguagesWidget username="mohammadaliiter" />}
        />
      </Grid>

      <Card className="w-full mb-8 bg-gray-800 bg-opacity-50">
        <Heading level={2} className="text-2xl font-semibold mb-4">🏆 Achievements</Heading>
        <GitHubTrophiesWidget username="mohammadaliiter" />
      </Card>

      <Card className="w-full bg-gray-800 bg-opacity-50">
        <Heading level={2} className="text-2xl font-semibold mb-4">💡 Fun Fact</Heading>
        <Text>
          When I'm not coding, you'll find me solving intricate puzzles or exploring the latest tech trends. 
          I believe in the power of continuous learning and enjoy sharing my knowledge through online programming tutoring.
        </Text>
      </Card>

      <Text className="mt-8 text-sm opacity-75">
        {`Profile views: `}
        <Image
          src="https://komarev.com/ghpvc/?username=mohammadaliiter&label=Profile%20Views&color=0e75b6&style=flat"
          alt="Profile Views"
          className="inline"
        />
      </Text>
    </Flex>
  )
}

// Note: The following components are placeholders and would need to be implemented separately
function GitHubStatsWidget({ username }) {
  return <Image src={`https://github-readme-stats.vercel.app/api?username=${username}&show_icons=true&theme=radical`} alt="GitHub Stats" />
}

function GitHubStreakWidget({ username }) {
  return <Image src={`https://github-readme-streak-stats.herokuapp.com/?user=${username}&theme=radical`} alt="GitHub Streak" />
}

function GitHubLanguagesWidget({ username }) {
  return <Image src={`https://github-readme-stats.vercel.app/api/top-langs/?username=${username}&layout=compact&theme=radical`} alt="Top Languages" />
}

function GitHubTrophiesWidget({ username }) {
  return <Image src={`https://github-profile-trophy.vercel.app/?username=${username}&theme=onedark&row=1&column=7`} alt="GitHub Trophies" />
}
