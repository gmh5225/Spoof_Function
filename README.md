# Spoof_Function
Spoofer your function into your cheats

just add SPOOF_FUNC in all your functions

like this

int abwe()
{
	SPOOF_FUNC

	unsigned long thread_hide_from_debugger = 0x11;

	const auto ntdll = LI_FN(LoadLibraryA).safe()(skCrypt("ntdll.dll"));

	if (ntdll == INVALID_HANDLE_VALUE || ntdll == NULL) { return false; }

	_NtQueryInformationProcess NtQueryInformationProcess = NULL;
	NtQueryInformationProcess = (_NtQueryInformationProcess)LI_FN(GetProcAddress).safe()(ntdll, skCrypt("NtQueryInformationProcess"));

	if (NtQueryInformationProcess == NULL) { return false; }

	(_NtSetInformationThread)(GetCurrentThread(), thread_hide_from_debugger, 0, 0, 0);

	return true;
}
