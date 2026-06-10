%global debug_package %{nil}
%global user prometheus
%global group prometheus

Name:    pushgateway
Version: 1.11.3
Release: 1%{?dist}
Summary: Prometheus push acceptor for ephemeral and batch jobs.
License: ASL 2.0
URL:     https://github.com/prometheus/pushgateway

Source0: https://github.com/prometheus/pushgateway/releases/download/v%{version}/%{name}-%{version}.linux-amd64.tar.gz
Source1: %{name}.unit
Source2: %{name}.default
Source3: _%{name}.init

%{?systemd_requires}
Requires(pre): shadow-utils

%description
The Prometheus Pushgateway exists to allow ephemeral and batch jobs to
expose their metrics to Prometheus. Since these kinds of jobs may not
exist long enough to be scraped, they can instead push their metrics to
a Pushgateway. The Pushgateway then exposes these metrics to Prometheus.

%prep
%setup -q -n %{name}-%{version}.linux-amd64

%build
/bin/true

%install
mkdir -vp %{buildroot}%{_sharedstatedir}/prometheus
install -D -m 755 %{name} %{buildroot}%{_bindir}/%{name}
install -D -m 644 %{SOURCE2} %{buildroot}%{_sysconfdir}/default/%{name}
install -D -m 644 %{SOURCE1} %{buildroot}%{_unitdir}/%{name}.service

%pre
getent group prometheus >/dev/null || groupadd -r prometheus
getent passwd prometheus >/dev/null || \
useradd -r -g prometheus -d %{_sharedstatedir}/prometheus -s /sbin/nologin -c "Prometheus services" prometheus
exit 0

%post
%systemd_post %{name}.service

%preun
%systemd_preun %{name}.service

%postun
%systemd_postun %{name}.service

%files
%defattr(-,root,root,-)
%{_bindir}/%{name}
%config(noreplace) %{_sysconfdir}/default/%{name}
%dir %attr(755, %{user}, %{group}) %{_sharedstatedir}/prometheus
%{_unitdir}/%{name}.service

%changelog
* Wed Jun 10 2026 Ivan Garcia <igarcia@cloudox.org> - 1.11.3
- Initial packaging for the 1.11.3 branch
