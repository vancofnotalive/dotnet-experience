# dotnet-experience

1) When you have trouble in email not sending at production, but it works on local machine in visual studio
the issue might be because of using "Directory.GetCurrentDirectory()" which is blocked in hostings so always use AppContext.BaseDirectory
And write this in .csproject of the project:
	<ItemGroup>
		<Content Include="MailKit/Templates/RegistrationCode.html">
			<CopyToOutputDirectory>Always</CopyToOutputDirectory>
		</Content>
	</ItemGroup>
In the include write the file path
